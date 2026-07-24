import java.util.LinkedList;

class MyHashSet {
    private static final int BUCKETS = 769; // A prime number to reduce collisions
    private LinkedList<Integer>[] table;

    @SuppressWarnings("unchecked")
    public MyHashSet() {
        table = new LinkedList[BUCKETS];
        for (int i = 0; i < BUCKETS; i++) {
            table[i] = new LinkedList<>();
        }
    }

    private int hash(int key) {
        return key % BUCKETS;
    }

    public void add(int key) {
        int index = hash(key);
        if (!table[index].contains(key)) {
            table[index].add(key);
        }
    }

    public void remove(int key) {
        int index = hash(key);
        table[index].remove((Integer) key);
    }

    public boolean contains(int key) {
        int index = hash(key);
        return table[index].contains(key);
    }
}
