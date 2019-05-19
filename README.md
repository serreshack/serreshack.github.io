> Serres Hackathon 4.0 - Java JPrime Quiz 2019

# Java JPrime 2019 Quiz

## Description
Answer the question in our java quiz and get the chance to win a ticket to the JPrime conference, in Sofia Bulgaria on the 28th and 29th of May, 2019.
If more than one person answers correctly, there will be a draw and the winner will be decided using a random number generator.

## Question

What will the following code print ... and why?:

```
public class Main {
    static class Person {
        private String name;
        public Person(String name) {
            this.name = name;
        }
        public void setName(String name) {
            this.name = name;
        }
        @Override
        public boolean equals(Object o) {
            if (this == o) return true;
            if (o == null || getClass() != o.getClass()) return false;
            Person person = (Person) o;
            return Objects.equals(name, person.name);
        }
        @Override
        public int hashCode() {
            return Objects.hash(name);
        }
    }

    public static void main(String[] args) {
        Person nikos = new Person ("nikos");
        Map<Person,String> map = new HashMap<>();
        map.put(nikos,"Manager");
        Person otherNikos = new Person("nikos");
        
        System.out.println(map.get(otherNikos)!=null
        	?"Nikos exists"
				:"Nikos does not exist");
				
        otherNikos.setName("Nicholas");
        nikos.setName("Nicholas");
        System.out.println(map.get(otherNikos)!=null
        	? "Nikos exists"
				:"Nikos does not exist");
    }
}
```
