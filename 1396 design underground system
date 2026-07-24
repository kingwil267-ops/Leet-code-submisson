import java.util.*;

class UndergroundSystem {

    // Helper class to store check-in information
    private static class CheckIn {
        String stationName;
        int time;

        CheckIn(String stationName, int time) {
            this.stationName = stationName;
            this.time = time;
        }
    }

    // Helper class to store total travel time and trip count
    private static class RouteData {
        double totalTime = 0;
        int count = 0;
    }

    // Maps customer id -> CheckIn info
    private Map<Integer, CheckIn> checkIns;
    
    // Maps "startStation->endStation" -> RouteData
    private Map<String, RouteData> routeMap;

    public UndergroundSystem() {
        checkIns = new HashMap<>();
        routeMap = new HashMap<>();
    }
    
    public void checkIn(int id, String stationName, int t) {
        checkIns.put(id, new CheckIn(stationName, t));
    }
    
    public void checkOut(int id, String stationName, int t) {
        // Retrieve and remove customer check-in record
        CheckIn checkIn = checkIns.remove(id);
        
        int travelTime = t - checkIn.time;
        String routeKey = checkIn.stationName + "->" + stationName;

        // Get or create route tracking data
        RouteData data = routeMap.computeIfAbsent(routeKey, k -> new RouteData());
        data.totalTime += travelTime;
        data.count += 1;
    }
    
    public double getAverageTime(String startStation, String endStation) {
        String routeKey = startStation + "->" + endStation;
        RouteData data = routeMap.get(routeKey);
        return data.totalTime / data.count;
    }
}
