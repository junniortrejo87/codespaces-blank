#include <iostream>
#include <fstream>
#include <sstream>
#include <array>

using namespace std;

// Define number of columns and rows in the CSV file
const int NUM_COLUMNS = 100;
const int NUM_ROWS = 100;

// Function to read the contents of the file and return as a string
string FileDataString(const string& path) {
    auto ss = ostringstream{};
    ifstream input_file(path);
    // Check if the file was opened successfully
    if (!input_file.is_open()) {
        cout << "Could not open the file - '"
            << path << "'" << endl;
        exit(EXIT_FAILURE);
    }
    // Read the contents of the file into the string stream
    ss << input_file.rdbuf();
    return ss.str();
}

// Function to display the contents of the CSV file
void display_data_csv(const array<array<string, NUM_COLUMNS>, NUM_ROWS>& csv_data, const int rows) {
    cout << "Displaying CSV Contents:" << endl;
    // Loop through each row and display its contents
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < NUM_COLUMNS; ++j) {
            cout << csv_data[i][j] << "    ";
        }
        cout << endl;
    }
}

int main()
{
    // Name of the CSV file
    string filename("Project_0_Data.csv");
    string file_contents;
    // Array to store the contents of the CSV file
    array<array<string, NUM_COLUMNS>, NUM_ROWS> csv_contents;
    // Delimiter used to separate values in the CSV file
    char delimiter = ',';

    // Read the contents of the file
    file_contents = FileDataString(filename);

    // Use an input string stream to parse the file contents
    istringstream sstream(file_contents);
    array<string, NUM_COLUMNS> items;
    string record;

    int row_counter = 0;
    int item_counter = 0;
    // Loop through each line in the file
    while (getline(sstream, record)) {
        // Use another input string stream to parse the values in the line
        istringstream line(record);
        item_counter = 0;
        // Loop through each value in the line
        while (getline(line, record, delimiter)) {
            items[item_counter] = record;
            item_counter += 1;
        }
        // Store the values in the array
        csv_contents[row_counter] = items;
        row_counter += 1;
    }

    //=========================================================================================
    int x;
    cout << "=========================================================" << endl;
    cout << "========Music Library========\n";
    cout << "1. Display All Songs\n";
    cout << "2. Add Song\n";
    cout << "3. Remove Song\n";
    cout << "4. Exit"<< endl;
    cout << "Type your choice:: ";
    cin >> x;

    if (x == 1) {
        // Display the contents of the CSV file
        display_data_csv(csv_contents, row_counter);
    }
    else if (x ==2) {
        exit(EXIT_FAILURE);
    }
    else if (x == 3) {

    }
    else if (x == 4) {

    }
    else {
        cout << "Not a an option in Menu" << endl;
    }
   

    // Exit the program
    exit(EXIT_SUCCESS);
