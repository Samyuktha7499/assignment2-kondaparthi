# assignment2-kondaparthi
# Samyuktha Kondaparthi
###### My Favourite place
Vizag , formerly known as  **Vishakapatanam which is the largest city** and the proposed **administrative capital** of the Indian state of Andhra Pradesh. It lies between the Eastern Ghats and the coast of the Bay of Bengal. It is the second largest city in the East cost of India after Chennai and also the fourth largest city in South India. It is one of the four smart cities of Andhra pradesh selected under Smart Cities Mission.
It also serves as the headquarters of Visakhapatnam district With an estimated output of $43.5 billion, the city is the ninth largest contributor to India's overall Gross domestic product as of 2016.

---

## Directions from maryville to vizag
1. Take flight from kansas city to hyderabad.
2. Take car from hyderabad to vizag.
   1.	Head east on Hyderabad - Janagam Hwy/Koti Women's College Rd/Main Rd Continue to follow Hyderabad - Janagam Hwy/Main Rd Pass by Venkateshwara Medical Store (850 m)
   2.	Follow NH65 and NH16 to Andhra Pradesh 6 hr 13 min (349 km)
   3.	Take GNT Road, Rajahmundry Rd and Godavari Fourth Bridge to NH16 1 hr 46 min (83.4 km)
   4.	Follow NH16 to Narsipatnam Road/Narsipatnam Tallapalem Rd 2 hr 33 min (145 km)
   5.	Continue straight past 9 TEA SHOP onto NH1 Pass by church (on the left 17.9 km.Continue straight through Gandepalli Jct to stay on NH16 Pass by Sebhari Internet And Xerox (on the left) 17.6 km
   6.	Continue straight past sri lakshmi ganapathi enterprises to stay on NH16 Pass by Satya Karnakula (on the left) 12.5 km
   7.	Continue straight to stay on NH16 Pass by MAHARAJA FAMILY RESTAURANT (on the right in 2.3 km) 8.6 km Keep right to stay on NH16 Pass by Tiffin (on the left in 8.5 km) 73.1 km
   8.	Take Rajam - Mallam Rd, Kasimkota Bangarumetta Rd/Kundram Rd and Vaddadi Madugula Paderu Dumbriguda Araku Rd to NH 516E 2 hr 20 min (82.6 km)
   9.	Turn right at Usman Kirana & General Stores onto NH 516
3. Destination has arrived enjoy the beaches and beautiful greenary.
## Items to be brought
 * Nice pair of clothes
 * Shoes
 * Camera
 * Snacks
    * chips
    * Drinks
    
**[Link to navigate to about me](AboutMe.md)**
   
   ---

   Everybody needs food to eat. Some people enjoy eating in a restaurant, and some people enjoy making their own meals at home. I'm attaching recommended food items list in below table.
   ### Creating table for famous foods/drinks available places

 |Items	            | Items available places | Approx pay  |
 |---               |---                     |---:
 |Bamboo chicken	| Araku	                 | 500 rupess  |
 |panipuri          | India	                 | 50 rupees   |
 |Gongura mutton	| Godavari	             | 1000 rupees |
 |Maggie            | hyderabad              | 50 rupees   |
 | Dhahi vada       | khammam                | 30 rupees   |
  
  ---

  # code fencing 
  The divide-and-conquer paradigm is often used to find an optimal solution of a problem. Its basic idea is to decompose a given problem into two or more similar, but simpler, subproblems, to solve them in turn, and to compose their solutions to solve the given problem. Problems of sufficient simplicity are solved directly. For example, to sort a given list of n natural numbers, split it into two lists of about n/2 numbers each, sort each of them in turn, and interleave both results appropriately to obtain the sorted version of the given list (see the picture). This approach is known as the merge sort algorithm.
  Refer for more <https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm>

```
  int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}

int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
}
```
For more <https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>