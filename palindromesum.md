int sum = 0;
	
	while (n>0) {
		int d = n%10;
		sum += d;
		n /= 10;
	}
	
	int o = sum;
	long r = 0;
	
	while (sum>0) {
		int d = sum % 10;
		r = r * 10 + d;
		sum /= 10;
	}
	
	if (r == o) {
		return true;
	}
	else {
		return false;
	}
}
};
