
#define _CRT_SECURE_NO_WARNING

#include <stdio.h>


int main() {
   
   /*
        n = 공의 개수
        m = 공 바꾸는 횟수
        a = 바꿀 바구니 1
        b = 바꿀 바구니 2
        j = 바구니 임시 저장 변수
        k = 바구니 배열
    */
    int n, m, a, b, j, k[100];

    // 공의 개수와 공을 바꾸는 횟수를 입력받는다.
    scanf("%d %d", &n, &m);

    // 바구니 배열에 n개 만큼의 공을 넣는다.
    for (int i = 0; i < n; i++) k[i] = i + 1;

    // m번 공을 바꾼다.
    for (int i = 0; i < m; i++) {
        // 바꿀 바구니 2개를 입력받는다.
        scanf("%d %d", &a, &b);

        // 바꿀 바구니 1을 j에 저장한다.
        j = k[a - 1];

        // 바꿀 바구니 1을 바꿀 바구니 2와 바꾼다.
        k[a - 1] = k[b - 1];

        // 바꿀 바구니 2를 저장해둔 j(바구니 1)와 바꾼다.
        k[b - 1] = j;
    }

    // 바뀐 바구니들의 순서에 맞게 공들을 출력한다.
    for (int i = 0; i < n; i++) printf("%d ", k[i]);

    return 0;
}
