# Generates a stream from a collection
Generates a stream based on the elements from the collection<br>
<img width="325" alt="console" src="https://github.com/danielurra/generates-a-stream-from-a-collection/assets/51704179/ff25d083-32e6-4549-aa47-9f9e703fc97c"><br>
# Grab the code
```java
package package_page392;

import java.time.Year;
import java.util.List;

public class Page392CreationOfStreamFromCollection {
	/**
	 * The Collection<E> interface and the Arrays utility class both provide a
	 * stream() method that builds a stream from the elements of a collection or an
	 * array. In the loop-based solution below, elements from the "values" list are
	 * processed using a for(:) loop to test whether a year is after the year 2000.
	 * The strings in the list are parsed to a Year object before being tested in an
	 * if statement.
	 */

	public static void main(String[] args) {
		System.out.println("Loop-based solution:");
		// Loop-based solution:
		List<String> values = List.of("2001", "1999", "2021", "2023", "2024", "1978");
		for (String s : values) {
			Year y = Year.parse(s);
			if (y.isAfter(Year.of(1975))) {
				System.out.println(s + " "); //
			}
		}
		/*
		 * The stream() operation at (1) generates a stream based on the elements from
		 * the collection. The map() operation at (2) parses the string elements to a
		 * Year object, as defined by the lambda expression that implements the Function
		 * interface. The filter() operation at (3) performs a filtering of the elements
		 * in the stream that are after the year 2000, as defined by a lambda expression
		 * that implements the Predicate interface. The forEach() operation at (4)
		 * performs an action on each stream element, as defined by a lambda expression
		 * that implements the Consumer interface. The loop-based solution specifies how
		 * the operations should be performed. The stream-based solution states what
		 * operations should be performed, qualified by the implementation of an
		 * appropriate functional interface. Stream-based solutions to many problems can
		 * be elegant and concise compared to their iteration-based counterparts.
		 */
		System.out.println("Stream-based solution:");
		// Stream-based solution:
		List<String> values2 = List.of("2001", "1999", "2021", "1111", "1112", "1113");
		values2.stream() // (1)
				.map(s -> Year.parse(s)) // (2)
				.filter(y -> y.isAfter(Year.of(1975))) // (3)
				.forEach(y -> System.out.println(y + " ")); // (4)

	}
}
```
