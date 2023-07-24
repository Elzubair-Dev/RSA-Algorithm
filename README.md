# RSA-Algorithm
The RSA algorithm is one of the most common and strong algorithms in the field of network security and cryptography

#### It works with uppercase words only.  

## Code:

```
using namespace std;
#include <stdio.h>
#include <iostream>
#include <string.h>
#include <math.h>

int d_call(float, int);

float phi;
int e, d, p, q, c, n, m;
char tab2[] = { 'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z' };
int tab1[] = { 2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27 };
char om_c[200];
char em_c[200];
int em[200];
int om[200];

void encryption()
{
	cout << "enter public key:";
	cin >> e;
	cout << "enter the first prime:";
	cin >> p;
	cout << "enter the second prime:";
	cin >> q;
	n = p * q;
	cout << "enter the original message:\n";
	cin >> om_c;
	for (int i = 0; i < sizeof(om_c); i++)
	{
		for (int j = 0; j < 26; j++)
		{
			if (om_c[i] == tab2[j])
			{
				em[i] = tab1[j];
				om[i] = int(pow(em[i], e)) % n;
				break;
			}
		}
	}
	cout << "The encrypted message:" << endl;
	for (int i = 0; i < sizeof(om_c); i++)
	{
		for (int j = 0; j < 26; j++)
		{
			if (om[i] == tab1[j])
			{
				em_c[i] = tab2[j];
				cout << em_c[i];
				break;
			}
		}
	}
	cout << "" << endl;
}

void decryption() {
	cout << "enter public key:";
	cin >> e;
	cout << "enter the first prime:";
	cin >> p;
	cout << "enter the second prime:";
	cin >> q;
	n = p * q;
	phi = (p - 1) * (q - 1);
	d = d_call(phi, e);
	cout << "enter the encrypted message:\n";
	cin >> em_c;
	for (int i = 0; i < sizeof(em_c); i++)
	{
		for (int j = 0; j < 26; j++)
		{
			if (em_c[i] == tab2[j])
			{
				em[i] = tab1[j];
				om[i] = int(pow(em[i], d)) % n;
				break;
			}
		}
	}
	cout << "The orginal message:" << endl;
	for (int i = 0; i < sizeof(em_c); i++)
	{
		for (int j = 0; j < 26; j++)
		{
			if (om[i] == tab1[j])
			{
				om_c[i] = tab2[j];
				cout << om_c[i];
				break;
			}
		}
	}
	cout << " " << endl;
}

void main()
{
	char process;
	cout << "Press 'e' for Encryption and 'd' for Decryption\n";
	cout << "Process is ";
	cin >> process;
	cout << "\n";
	switch (process)
	{
	case 'e': {
		cout << "Encryption ...\n";
		cout << "______________\n\n";
		encryption();
	}; break;
	case 'd': {
		cout << "Decryption ...\n";
		cout << "______________\n\n";
		decryption(); 
	}; break;
	default: cout << "Please choose either small 'e' or small 'd'\n";break;
	}
}
int d_call(float phi, int e)
{
	for (int d = 1; d < 11; d++)
		if (phi / (e * d - 1) == 1) return d;
}

```

## Buy me a Coffee:
if you want to support me (https://www.buymeacoffee.com/zu698air)

#### Don't forgit to give me a Star

## Done
