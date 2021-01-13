# aoe2dataset

## What is this?
This repo currently holds a dataset of 100 analyzed Age Of Empires II: Definitive Edition matches.
* New states are recorded approx every 20 in-game seconds.
* The files are stored as .recinfo but should be seen as json files.

### AOE Version
Age Of Empires II: Definitive Edition (13.34 101.101.43210.0)

### Player data distribution
![PlayerData](dataset/v1/1v1%20Arabia%20top%20players/datasetplayersummary.png?raw=true "Player data distribution")

## Why?
To share replay analysis from aoe2 matches to enable new projects to be created.

## Goal
To create enough data that ML/DL applications will output interesting results.

## Missing data / Known errors
* Analyzed files unfortunately doesn't include tech upgrades except the total amount.
* Units, buildings and objects may contain errornous widths and heights.

## Code

### JSON structure in C#
```c#
public class RecInfo
{
    public GameState[] gameStates { get; set; }
    public string version { get; set; }
    public string winner { get; set; }
}

public class GameState
{
    public Map map { get; set; }
    public PlayerMain playerMain { get; set; }
    public int time { get; set; }
}

public class Map
{
    public MapObject[] mapObjects { get; set; }
    public MapObjectsSummary mapObjectsSummary { get; set; }
}

public class MapObjectsSummary
{
    public int berryCount { get; set; }
    public int berryLeft { get; set; }
    public int boarCount { get; set; }
    public int boarFoodLeft { get; set; }
    public int deerCount { get; set; }
    public int deerFoodLeft { get; set; }
    public int fishCount { get; set; }
    public int fishLeft { get; set; }
    public int goldLeft { get; set; }
    public int goldMineCount { get; set; }
    public int sheepCount { get; set; }
    public int sheepFoodLeft { get; set; }
    public int stoneLeft { get; set; }
    public int stoneMineCount { get; set; }
    public int treeCount { get; set; }
    public int woodLeft { get; set; }
}

public class MapObject
{
    public string n { get; set; }
    public Pos p { get; set; }
    public float r { get; set; }
    public float x { get; set; }
    public float y { get; set; }
}

public class PlayerMain
{
    public Player[] players { get; set; }
}

public class Player
{
    public string civilization { get; set; }
    public int colorId { get; set; }
    public GameObjectSummary gameObjectSummary { get; set; }
    public string name { get; set; }
    public ObjectList objectList { get; set; }
    public Resources resources { get; set; }
}

public class GameObjectSummary
{
    public BuildingSummary buildingSummary { get; set; }
    public UnitSummary unitSummary { get; set; }
}

public class BuildingSummary
{
    public int archeryRangeCount { get; set; }
    public int barracksCount { get; set; }
    public int blacksmithCount { get; set; }
    public int bombardTowerCount { get; set; }
    public int castleCount { get; set; }
    public int dockCount { get; set; }
    public int farmCount { get; set; }
    public int feitoriaCount { get; set; }
    public int fishTrapCount { get; set; }
    public int fortifiedWallCount { get; set; }
    public int gateCount { get; set; }
    public int guardTowerCount { get; set; }
    public int houseCount { get; set; }
    public int keepCount { get; set; }
    public int krepostCount { get; set; }
    public int lumberCampCount { get; set; }
    public int marketCount { get; set; }
    public int millCount { get; set; }
    public int miningCampCount { get; set; }
    public int monasteryCount { get; set; }
    public int outpostCount { get; set; }
    public int palisadeGateCount { get; set; }
    public int palisadeWallCount { get; set; }
    public int siegeWorkshopCount { get; set; }
    public int stableCount { get; set; }
    public int stoneWallCount { get; set; }
    public int townCenterCount { get; set; }
    public int universityCount { get; set; }
    public int watchTowerCount { get; set; }
    public int wonderCount { get; set; }
}

public class UnitSummary
{
    public int arbalesterCount { get; set; }
    public int archerCount { get; set; }
    public int batteringRamCount { get; set; }
    public int battleElephantCount { get; set; }
    public int bombardCannonCount { get; set; }
    public int camelRiderCount { get; set; }
    public int cannonGalleonCount { get; set; }
    public int cappedRamCount { get; set; }
    public int caravelCount { get; set; }
    public int cavalierCount { get; set; }
    public int cavalryArcherCount { get; set; }
    public int championCount { get; set; }
    public int condottieroCount { get; set; }
    public int crossbowmanCount { get; set; }
    public int demolitionRaftCount { get; set; }
    public int demolitionShipCount { get; set; }
    public int eagleScoutCount { get; set; }
    public int eagleWarriorCount { get; set; }
    public int eliteBattleElephantCount { get; set; }
    public int eliteCannonGalleonCount { get; set; }
    public int eliteCaravelCount { get; set; }
    public int eliteEagleWarriorCount { get; set; }
    public int eliteGenitourCount { get; set; }
    public int eliteLongboatCount { get; set; }
    public int eliteSkirmisherCount { get; set; }
    public int eliteSteppeLancerCount { get; set; }
    public int eliteTurtleShipCount { get; set; }
    public int farmerCount { get; set; }
    public int fastFireShipCount { get; set; }
    public int fireGalleyCount { get; set; }
    public int fireShipCount { get; set; }
    public int fishingShipCount { get; set; }
    public int foragerCount { get; set; }
    public int galleonCount { get; set; }
    public int galleyCount { get; set; }
    public int genitourCount { get; set; }
    public int goldMinerCount { get; set; }
    public int halberdierCount { get; set; }
    public int handCannoneerCount { get; set; }
    public int heavyCamelRiderCount { get; set; }
    public int heavyCavalryArcherCount { get; set; }
    public int heavyDemolitionShipCount { get; set; }
    public int heavyScorpionCount { get; set; }
    public int hunterCount { get; set; }
    public int hussarCount { get; set; }
    public int idleTradeCartCount { get; set; }
    public int idleVills { get; set; }
    public int imperialCamelRiderCount { get; set; }
    public int imperialSkirmisherCount { get; set; }
    public int knightCount { get; set; }
    public int lightCavalryCount { get; set; }
    public int longSwordsmanCount { get; set; }
    public int longboatCount { get; set; }
    public int lumberjackCount { get; set; }
    public int manAtArmsCount { get; set; }
    public int mangonelCount { get; set; }
    public int militiaCount { get; set; }
    public int missionaryCount { get; set; }
    public int monkCount { get; set; }
    public int onagerCount { get; set; }
    public int paladinCount { get; set; }
    public int petardCount { get; set; }
    public int pikemanCount { get; set; }
    public int scorpionCount { get; set; }
    public int scoutCavalryCount { get; set; }
    public int shepherdCount { get; set; }
    public int siegeOnagerCount { get; set; }
    public int siegeRamCount { get; set; }
    public int siegeTowerCount { get; set; }
    public int skirmisherCount { get; set; }
    public int slingerCount { get; set; }
    public int spearmanCount { get; set; }
    public int steppeLancerCount { get; set; }
    public int stoneMinerCount { get; set; }
    public int tradeCartCount { get; set; }
    public int tradeCogCount { get; set; }
    public int transportShipCount { get; set; }
    public int trebuchetCount { get; set; }
    public int turtleShipCount { get; set; }
    public int twoHandedSwordsmanCount { get; set; }
    public int uniqueUnitCount { get; set; }
    public int warGalleyCount { get; set; }
}

public class ObjectList
{
    public int count { get; set; }
    public Object[] objects { get; set; }
}

public class Object
{
    public string n { get; set; }
    public Pos p { get; set; }
    public float r { get; set; }
}

public class Pos
{
    public float h { get; set; }
    public float w { get; set; }
    public float x { get; set; }
    public float y { get; set; }
}

public class Resources
{
    public int age { get; set; }
    public int buildingsRazed { get; set; }
    public int deaths { get; set; }
    public int food { get; set; }
    public int gold { get; set; }
    public int kills { get; set; }
    public int mapExplored { get; set; }
    public int militaryCount { get; set; }
    public int population { get; set; }
    public int populationUntilHoused { get; set; }
    public int relicCount { get; set; }
    public int relicGold { get; set; }
    public int stone { get; set; }
    public int totalCastles { get; set; }
    public int totalFood { get; set; }
    public int totalGold { get; set; }
    public int totalResearchCount { get; set; }
    public int totalStone { get; set; }
    public int totalWood { get; set; }
    public int villagerCount { get; set; }
    public int wood { get; set; }
}
```
