#include <iostream>

using namespace std;


string GetStdoutFromCommand(string cmd) {

    string data;
    FILE * stream;
    const int max_buffer = 256;
    char buffer[max_buffer];
    cmd.append(" 2>&1");

    stream = popen(cmd.c_str(), "r");

    if (stream) {
        while (!feof(stream))
    if (fgets(buffer, max_buffer, stream) != NULL) data.append(buffer);
        pclose(stream);
    }

    return data;
}

int main () {

    string exitFlag = "";

    while (true) {
        cout << "########################" << endl << endl;
        cout << "Write 'memory' to get info about memory card" << endl;
        cout << "Write 'mother' to get info about motherboar" << endl;
        cout << "Write 'processor' to get info about processor" << endl;
        cout << "Write 'q' (or press ctrl+c) to exit" << endl << endl;
        cout << "########################" << endl;

        cout << endl << "$ ";
        cin >> exitFlag;
        cout << endl;

        if (exitFlag == "exit")
            break;

        if (exitFlag == "memory") {

            string memory = GetStdoutFromCommand("dmidecode --type memory"); 
            cout << "Memory: " << memory << endl;

        } else if (exitFlag == "mother") {

            string motherBoard = GetStdoutFromCommand("dmidecode --type motherboard"); 
            cout << "Memory: " << motherBoard << endl;

        } else if (exitFlag == "processor") {

            string processor = GetStdoutFromCommand("dmidecode --type processor"); 
            cout << "Memory: " << processor << endl;

        } else if (exitFlag == "q") {
            
            break;

        } else {
            cout << "Your command is inc" << endl;
        }
    }

    return 0;
}
