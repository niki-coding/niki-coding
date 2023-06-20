#include <iostream>
#include <string>

class Room {
protected:
    std::string flooring;

public:
    Room(const std::string& flooring) : flooring(flooring) {}
};

class LivingRoom : public Room {
private:
    std::string couch;
    std::string tv;

public:
    LivingRoom(const std::string& flooring, const std::string& couch, const std::string& tv)
        : Room(flooring), couch(couch), tv(tv) {}
};

class Kitchen : public Room {
private:
    std::string kitchenStuff;
    std::string counter;

public:
    Kitchen(const std::string& flooring, const std::string& kitchenStuff, const std::string& counter)
        : Room(flooring), kitchenStuff(kitchenStuff), counter(counter) {}
};

class Foyer {
private:
    std::string frontDoor;
    std::string shoeRack;
    std::string stairs;

public:
    Foyer(const std::string& frontDoor, const std::string& shoeRack, const std::string& stairs)
        : frontDoor(frontDoor), shoeRack(shoeRack), stairs(stairs) {}
};

class Bathroom : public Room {
public:
    Bathroom(const std::string& flooring) : Room(flooring) {}
};

class Bedroom : public Room {
private:
    std::string desk;
    std::string walkInWardrobe;
    std::string ensuite;
    std::string bed;

public:
    Bedroom(const std::string& flooring, const std::string& desk, const std::string& walkInWardrobe,
            const std::string& ensuite, const std::string& bed)
        : Room(flooring), desk(desk), walkInWardrobe(walkInWardrobe), ensuite(ensuite), bed(bed) {}
};

class House {
private:
    LivingRoom livingRoom;
    Kitchen kitchen;
    Bathroom kitchenBathroom;
    Bathroom upstairsBathroom;
    Foyer foyer;
    Bedroom masterBedroom;
    Bedroom secondBedroom;
    Bedroom thirdBedroom;
    std::string laundryRoom;

public:
    House() :
        livingRoom("carpet", "couch", "TV"),
        kitchen("marble", "kitchen stuff", "counter"),
        kitchenBathroom("marble"),
        upstairsBathroom("marble"),
        foyer("front door", "shoe rack", "stairs"),
        masterBedroom("marble", "desk", "walk-in wardrobe", "ensuite", "triple bed"),
        secondBedroom("marble", "desk", "walk-in wardrobe", "ensuite", "double bed"),
        thirdBedroom("marble", "desk", "walk-in wardrobe", "ensuite", "bunk bed"),
        laundryRoom("laundry room") {}

    // ... Additional methods or functionality for the House class ...
};

int main() {
    House house;

    // You can access the rooms and their properties using the house object, for example:
    std::cout << "Living Room Flooring: " << house.livingRoom.flooring << std::endl;
    std::cout << "Kitchen Counter: " << house.kitchen.counter << std::endl;
    std::cout << "Foyer Shoe Rack: " << house.foyer.shoeRack << std::endl;
    std::cout << "Master Bedroom Bed: " << house.masterBedroom.bed << std::endl;

    return 0;
}
