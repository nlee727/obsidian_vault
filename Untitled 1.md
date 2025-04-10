#ifndef RECCHECK
#include <set>
#include <iostream>
#include <fstream>
#include <string>
#include <vector>
#include <map>
// add or remove necessary headers as you please

#endif

#include "schedwork.h"

using namespace std;

// a constant that can be used to indicate an INVALID 
// worker ID if that is useful to your implementation.
// Feel free to not use or delete.
static const Worker_T INVALID_ID = (unsigned int)-1;


// Add prototypes for any helper functions here
bool findSchedule(size_t dayIndex, const AvailabilityMatrix& avail, size_t dailyNeed, size_t maxShifts, DailySchedule& sched, std::vector<size_t>& shiftsCount);
bool assignWorkers(size_t dayIndex, size_t workerIndex, const AvailabilityMatrix& avail, std::vector<Worker_T>& currentWorkers, DailySchedule& sched, std::vector<size_t>& shiftsCount, size_t dailyNeed, size_t maxShifts);
bool isWorkerAlreadyAssigned(const std::vector<Worker_T>& currentWorkers, Worker_T worker);

// Main scheduling function
bool schedule(
    const AvailabilityMatrix& avail,
    const size_t dailyNeed,
    const size_t maxShifts,
    DailySchedule& sched
) 
{
    if (avail.empty() || avail[0].empty()) {
        return false;
    }
    sched.clear();
    sched.resize(avail.size());
    std::vector<size_t> shiftsCount(avail[0].size(), 0);

    return findSchedule(0, avail, dailyNeed, maxShifts, sched, shiftsCount);
}


// find a valid schedule
bool findSchedule(size_t dayIndex, const AvailabilityMatrix& avail, size_t dailyNeed,
                  size_t maxShifts, DailySchedule& sched, std::vector<size_t>& shiftsCount) {
    if (dayIndex == avail.size()) {
        return true; 
    }

    std::vector<Worker_T> currentWorkers;
    return assignWorkers(dayIndex, 0, avail, currentWorkers, sched, shiftsCount, dailyNeed, maxShifts);
}

//assign workers for a particular day
bool assignWorkers(size_t dayIndex, size_t workerIndex, const AvailabilityMatrix& avail,
                   std::vector<Worker_T>& currentWorkers, DailySchedule& sched,
                   std::vector<size_t>& shiftsCount, size_t dailyNeed, size_t maxShifts) {
    if (currentWorkers.size() == dailyNeed) {
        sched[dayIndex] = currentWorkers;
        if (findSchedule(dayIndex + 1, avail, dailyNeed, maxShifts, sched, shiftsCount)) {
            return true;
        }
        return false;  
    }

    for (size_t i = workerIndex; i < avail[dayIndex].size(); ++i) {
        if (avail[dayIndex][i] && shiftsCount[i] < maxShifts) {
            if (!isWorkerAlreadyAssigned(currentWorkers, i)) {
                currentWorkers.push_back(i);
                shiftsCount[i]++;
                if (assignWorkers(dayIndex, i + 1, avail, currentWorkers, sched, shiftsCount, dailyNeed, maxShifts)) {
                    return true;
                }
                currentWorkers.pop_back();  // Backtrack: remove worker
                shiftsCount[i]--;  // Backtrack: decrement shift count
            }
        }
    }

    return false;
}

bool isWorkerAlreadyAssigned(const std::vector<Worker_T>& currentWorkers, Worker_T worker) {
    for (size_t j = 0; j < currentWorkers.size(); ++j) {
        if (currentWorkers[j] == worker) {
            return true;
        }
    }
    return false;
}