### 修改<br>
  # # include <stdio.h><br>
 # # include <stdbool.h><br>
int main() {<br>
    int code;<br>
    while(true){<br>
		printf("Show me your code,please.");<br>
        scanf("%d",code);<br>
        if(code >= 100000 || code <= 999999){printf("I am super hacker!");<br>
        return code;<br>
		}else printf("Fake code!");<br>
    }<br>
    return 0;<br>
}<br>
<br>
### helloc.c<br>
 # # include <stdio.h><br>
<br>
int main() {<br>
    printf("Hello, glimmer!");<br>
    return 0;<br>
}<br>
<br>
### 最大公约数<br>
 # # include <stdio.h><br>
<br>
int main(){<br>
	int m,n,c;<br>
	scanf("%d%d",&m,&n);<br>
	do{<br>
		if(m<n){<br>
		c=m;<br>
		m=n;<br>
		n=c;<br>
		}<br>
		c=m%n;<br>
		m=n;<br>
		n=c;<br>
	}while(c!=0);<br>
	printf("%d",m);<br>
	return 0;<br>
}