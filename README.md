# assignment2-bandari

# Anusha Bandari

###### Costa Rica’s

Temperatures in Costa Rica’s **cloud forests** tend to stay the same throughout the year.While it’s a year-round destination, December to May are the dry months and so they’re the best time to make the most of this **picturesque** destination.

****

# Directions for traveling from Maryville to Costa Rica


1.Firstly book a flight ticket
2.Before booking a flight ticket select the date,time,to and from address
3.Next make a confirmation of your booking
4.To travel from Maryville to Costa Rica firstly, we need to go to Kansas City.
    1.Kansas City  
    2.San Jose
5.The final destination is the place called Costa Rica

* Beaches
    * Montezuma Beach
    * Santa Teresa Beach
    * Whale Tail Beach
* Volcanoes        

---

[AboutMe](https://github.com/Anusha290699/assignment2-bandari/blob/main/AboutMe.md)

---

| Food/Drinks | Location | Price (Inr) |
| ---| ---| ---: |
| Mutton Biryani | Pardise | 400 |
| Coffee | Scooter's Coffee | 350 |
| Veggie Burger | KFC | 150  |
| Wrap | Starbucks | 250 |

---

### Quotes related to Strength

> "Do not judge me by my success, judge me by how many times I fell down and got back up again.” - *Nelson Mandela*
>
> “This is no time for ease and comfort. It is time to dare and endure.” - *Winston Churchill*

---

> Graham's scan is a method of finding the convex hull of a finite set of points in the plane with time complexity O(n log n). It is named after Ronald Graham, who published the original algorithm in 1972. The algorithm finds all vertices of the convex hull ordered along its boundary.
>
> continued.. <https://en.wikipedia.org/wiki/Graham_scan#:~:text=Graham's%20scan%20is%20a%20method,hull%20ordered%20along%20its%20boundary>

---

```
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }

    a.clear();
    for (int i = 0; i < (int)up.size(); i++)
        a.push_back(up[i]);
    for (int i = down.size() - 2; i > 0; i--)
        a.push_back(down[i]);
}
```

Next algorithm.. <https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html>