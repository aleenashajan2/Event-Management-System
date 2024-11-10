#include <iostream>
#include <string>
using namespace std;

class Event {
protected:
    string eventName;
    string eventDate;
    double duration;
    double foodBudget;
    double venueBudget;

public:
    Event(string name = "Unknown", string date = "01/01/2024", double dur = 0.0, double foodBud = 0.0, double venBud = 0.0)
        : eventName(name), eventDate(date), duration(dur), foodBudget(foodBud), venueBudget(venBud) {}

    void displayEventDetails() const {
        cout << "Event Name: " << eventName << endl;
        cout << "Event Date: " << eventDate << endl;
        cout << "Duration: " << duration << " hours" << endl;
        cout << "Food Budget: Rs." << foodBudget << endl;
        cout << "Venue Budget: Rs." << venueBudget << endl;
    }

    Event operator+(const Event& other) const {
        return Event(eventName + " & " + other.eventName,
                     eventDate, 
                     duration + other.duration,
                     foodBudget + other.foodBudget,
                     venueBudget + other.venueBudget);
    }

    bool operator==(const Event& other) const {
        return duration == other.duration;
    }
};

class Venue : public Event {
protected:
    string venueName;
    string location;

public:
    Venue(string name = "Unknown", string date = "01/01/2024", string venue = "Main Hall", string loc = "City Center", double dur = 0.0, double foodBud = 0.0, double venBud = 0.0)
        : Event(name, date, dur, foodBud, venBud), venueName(venue), location(loc) {}

    void displayVenueDetails() const {
        displayEventDetails();
        cout << "Venue: " << venueName << endl;
        cout << "Location: " << location << endl;
    }
};

class Booking : public Venue {
private:
    int seatsBooked;

public:
    Booking(string name = "Unknown", string date = "01/01/2024", string venue = "Main Hall", string loc = "City Center", double dur = 0.0, double foodBud = 0.0, double venBud = 0.0, int seats = 0)
        : Venue(name, date, venue, loc, dur, foodBud, venBud), seatsBooked(seats) {}

    void displayBookingDetails() const {
        displayVenueDetails();
        cout << "Seats Booked: " << seatsBooked << endl;
    }
};

int main() {
    int choice;
    do {
        string name, date, venue, location;
        double duration, foodBudget, venueBudget;
        int seats;

        cout << "Enter Event Name: ";
        cin.ignore();
        getline(cin, name);
        cout << "Enter Event Date (DD/MM/YYYY): ";
        getline(cin, date);
        cout << "Enter Venue Name: ";
        getline(cin, venue);
        cout << "Enter Venue Location: ";
        getline(cin, location);
        cout << "Enter Event Duration (in hours): ";
        cin >> duration;
        cout << "Enter Food Budget: Rs.";
        cin >> foodBudget;
        cout << "Enter Venue Budget: Rs.";
        cin >> venueBudget;
        cout << "Enter Seats Booked: ";
        cin >> seats;

        Booking eventBooking(name, date, venue, location, duration, foodBudget, venueBudget, seats);
        cout << "\nBooking Details:\n";
        eventBooking.displayBookingDetails();

        cout << "\nDo you want to enter another event? (1 for YES, 0 for NO): ";
        cin >> choice;

    } while (choice == 1);

    cout << "Thank you for using the Event Booking System.\n";
    return 0;
}
