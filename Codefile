#include <iostream>
#include <vector>
#include <list>
#include <queue>
#include <map>
#include <set>
#include <ctime>
#include <fstream>
using namespace std;

int hash_function(int e_num) {
    return e_num % 5;
}

struct Compare {
    bool operator()(const pair<pair<int, int>, int>& a, const pair<pair<int, int>, int>& b) {
        if (a.second != b.second)
            return a.second < b.second;
        else if (a.first.first != b.first.first)
            return a.first.first < b.first.first;
        else
            return a.first.second > b.first.second;
    }
};

void hashtable(int hash_key, vector<list<pair<int, int>>>& table, priority_queue<pair<pair<int, int>, int>, vector<pair<pair<int, int>, int>>, Compare>& pq, int value, int distance, set<tuple<int, int, int>>& existing) {
    if (existing.count({hash_key, value, distance})) {
        cout << "Duplicate emergency entry ignored." << endl;
        return;
    }
    table[hash_key].push_back({value, distance});
    pq.push({{value, distance}, hash_key});
    existing.insert({hash_key, value, distance});
}

void log_alert(int e_num, int severity, int distance) {
    ofstream log("alerts.txt", ios::app);
    time_t now = time(0);
    char* dt = ctime(&now);
    log << "Time: " << dt
        << "Emergency Number: " << e_num << ", Severity: " << severity << ", Distance: " << distance << "\n";
    log.close();
}

int main() {
    map<int, string> emergency_names = {
        {0, "FIREACCIDENT"},
        {1, "ROADACCIDENT"},
        {2, "HEARTSTROKE"},
        {3, "PREGNANCYALERT"},
        {4, "CHILDABUSE"}
    };

    cout << "This is the Emergency Alert Triggering System" << endl;
    cout << "NUMBER | EMERGENCY NAME   | THRESHOLD VALUE" << endl;
    for (const auto& [num, name] : emergency_names)
        cout << "  " << num << "     " << name << "\t\t" << (num + 1) * 100 << endl;

    vector<list<pair<int, int>>> table(5);
    priority_queue<pair<pair<int, int>, int>, vector<pair<pair<int, int>, int>>, Compare> pq;
    set<tuple<int, int, int>> existing_entries;

    int choice, e_num, value, distance;
    cout << "Type -1 to stop entering emergencies, or 1 to continue." << endl;
    cin >> choice;

    while (choice != -1) {
        cout << "Enter emergency number (0-4): ";
        cin >> e_num;
        if (e_num >= 5) {
            cout << "Invalid emergency number." << endl;
        } else {
            cout << "Enter severity value: ";
            cin >> value;
            cout << "Enter distance: ";
            cin >> distance;
            int hash_key = hash_function(e_num);
            hashtable(hash_key, table, pq, value, distance, existing_entries);
            log_alert(e_num, value, distance);
        }
        cout << "Continue? (-1 to stop): ";
        cin >> choice;
    }

    string modify;
    cout << "Do you want to modify (add/delete/search)? yes/no: ";
    cin >> modify;
    if (modify == "yes") {
        int cont = 1;
        while (cont) {
            cout << "1. Insert\n2. Delete\n3. Search\nChoice: ";
            int option;
            cin >> option;
            switch (option) {
                case 1:
                    cout << "Enter emergency number: ";
                    cin >> e_num;
                    if (e_num >= 5) {
                        cout << "Invalid number." << endl;
                        break;
                    }
                    cout << "Enter severity: ";
                    cin >> value;
                    cout << "Enter distance: ";
                    cin >> distance;
                    hashtable(hash_function(e_num), table, pq, value, distance, existing_entries);
                    log_alert(e_num, value, distance);
                    break;
                case 2:
                    cout << "Enter emergency number to delete: ";
                    cin >> e_num;
                    table[e_num].clear();
                    break;
                case 3:
                    cout << "Enter emergency number to search: ";
                    cin >> e_num;
                    for (auto val : table[e_num])
                        cout << "Severity: " << val.first << ", Distance: " << val.second << endl;
                    break;
                default:
                    cout << "Invalid option." << endl;
            }
            cout << "Continue modifying? 1-Yes, 0-No: ";
            cin >> cont;
        }
    }

    cout << "Final Hashtable Status:\n";
    for (int i = 0; i < 5; ++i) {
        cout << i << ": ";
        for (auto val : table[i])
            cout << "[Severity: " << val.first << ", Distance: " << val.second << "] ";
        cout << endl;
    }

    cout << "\nPriority Queue - Sorted Emergencies:\n";
    while (!pq.empty()) {
        auto top = pq.top(); pq.pop();
        int e_num = top.second, severity = top.first.first, distance = top.first.second;
        cout << "Emergency Number: " << e_num << " (" << emergency_names[e_num] << ")" << endl;
        cout << "Severity: " << severity << ", Distance: " << distance << endl;
        cout << "Precautions:\n";
        switch (e_num) {
            case 0:
                cout << "- Evacuate the area immediately.\n";
                cout << "- Use fire extinguishers if trained.\n";
                cout << "- Stay low to avoid smoke inhalation.\n";
                cout << "- Do not use elevators.\n";
                cout << "- Call: 101\n";
                break;
            case 1:
                cout << "- Assess the scene for hazards.\n";
                cout << "- Provide basic first aid if trained.\n";
                cout << "- Avoid moving injured persons unless necessary.\n";
                cout << "- Call: 108\n";
                break;
            case 2:
                cout << "- Look for chest pain or dizziness symptoms.\n";
                cout << "- Keep the person calm and still.\n";
                cout << "- Administer CPR if trained.\n";
                cout << "- Call: 108\n";
                break;
            case 3:
                cout << "- Keep the pregnant person comfortable.\n";
                cout << "- Place them on left side to improve circulation.\n";
                cout << "- Monitor vital signs.\n";
                cout << "- Call: 108\n";
                break;
            case 4:
                cout << "- Remove the child from danger.\n";
                cout << "- Document any visible signs discreetly.\n";
                cout << "- Offer emotional reassurance.\n";
                cout << "- Report to authorities.\n";
                cout << "- Call: 112\n";
                break;
        }
        cout << endl;
    }
    return 0;
}
