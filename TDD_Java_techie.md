# TDD - Test Driven Development ( Red | Green | Refactor ) | Example | Java Techie
- https://www.youtube.com/watch?v=UzRa5cLma0g&list=PLVz2XdJiJQxz_55RIJL8mjO6nx_T87LVD&index=18&ab_channel=JavaTechie
- github: https://github.com/Java-Techie-jt/tdd-example
![image](https://user-images.githubusercontent.com/69948118/224475590-1ae170a0-3a8d-41f1-be3f-e99f813c3d64.png)
![image](https://user-images.githubusercontent.com/69948118/224475600-f4aae5ca-c68c-4909-91cd-5ab6dc39d854.png)
![image](https://user-images.githubusercontent.com/69948118/224475605-4bde4ff6-eacd-4701-aa50-8e7b9725ddd2.png)
![image](https://user-images.githubusercontent.com/69948118/224475616-473451b2-b9b6-41fe-a45c-e4a1491e213a.png)
![image](https://user-images.githubusercontent.com/69948118/224475626-c60507cd-f9fc-4faa-abb3-e2f366cb4251.png)

```java
package com.javatechie.tdd_example;

import org.junit.Assert;
import org.junit.Test;

/**
 * Unit test for simple App.
 */
public class PopulationSearchTest

{
	
	
	
	@Test
	public void findPopulation() {
		String city="Bangalore";
		int expectedPopulationCount=200000;
		PopulationSearch ps=new PopulationSearch();
		int count=ps.getPopulation(city);
		Assert.assertEquals(expectedPopulationCount, count);
	}
	
	@Test(expected=NullPointerException.class)
	public void findPopulationWithEmptyInput() {
		String city="";
		int expectedPopulationCount=0;
		PopulationSearch ps=new PopulationSearch();
		int count=ps.getPopulation(city);
		Assert.assertEquals(expectedPopulationCount, count);
	}
	
	@Test(expected=NullPointerException.class)
	public void findPopulationWithInavlidInput() {
		String city="XYZ";
		int expectedPopulationCount=0;
		PopulationSearch ps=new PopulationSearch();
		int count=ps.getPopulation(city);
		Assert.assertEquals(expectedPopulationCount, count);
	}
}
```

```java
package com.javatechie.tdd_example;

import java.util.HashMap;
import java.util.Map;

/**
 * Hello world!
 *
 */
public class PopulationSearch {
	

	public int getPopulation(String city) {
		Map<String, Integer> populationMap = null;
		int populationCount = 0;
		if (city.isEmpty()) {
			throw new NullPointerException("input shouldn't be empty");
		}
		populationMap = getPopulationStatistic();
		if (!populationMap.containsKey(city)) {
			throw new NullPointerException("invalid input");
		} else {
			populationCount = populationMap.get(city);
		}
		return populationCount;
	}
	// user can give empty input
	// input may not be present in db

	private Map<String, Integer> getPopulationStatistic() {
		Map<String, Integer> populationMap = new HashMap<>();
		populationMap.put("Bangalore", 200000);
		populationMap.put("Hyderabad", 500000);
		populationMap.put("Pune", 300000);
		populationMap.put("Mumbai", 800000);
		return populationMap;
	}
}
```
