# printMaxActivities_algoritham

#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;
void printMaxActivities(int s[], int f[], int n)
{
    int i, j;

    printf ("Following activities are selected n");

    // The first activity always gets selected
    i = 0;
    printf("%d ", i);

    // Consider rest of the activities
    for (j = 1; j < n; j++)
    {
      // If this activity has start time greater than or
      // equal to the finish time of previously selected
      // activity, then select it
      if (s[j] >= f[i])
      {
          printf ("%d ", j);
          i = j;
      }
    }
}

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */
    int N;
    cin >> N;
    int s[N], f[N];
    for (int i = 0; i < N; i++) {
        cin >> s[i];
    }
    for (int j = 0; j <N; j++) {
        cout << s[j] << " ";
    }
    cout<<endl;

     for (int i = 0; i < N; i++) {
        cin >> f[i];
    }
    for (int j = 0; j <N; j++) {
        cout << f[j] << " ";
    }
      cout<<endl;
    printMaxActivities(s, f, N);
    return 0;
}
