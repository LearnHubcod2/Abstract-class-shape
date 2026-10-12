1. Shape.java (Abstract Class)

public abstract class Shape {
    public abstract double surface_area();
    public abstract double volume();
}

2. Sphere.java (Part 1)

public class Sphere extends Shape {
    private double radius;

    public Sphere(double radius) {
        this.radius = radius;
    }

    @Override
    public double surface_area() {
        return 4 * Math.PI * radius * radius;
    }

    @Override
    public double volume() {
        return (4.0 / 3) * Math.PI * radius * radius * radius;
    }

    @Override
    public String toString() {
        return "Sphere: Surface Area = " + surface_area() + ", Volume = " + volume();
    }
}

3. Cylinder.java (Part 2)

public class Cylinder extends Shape {
    private double radius;
    private double height;

    public Cylinder(double radius, double height) {
        this.radius = radius;
        this.height = height;
    }

    @Override
    public double surface_area() {
        return 2 * Math.PI * radius * (radius + height);
    }

    @Override
    public double volume() {
        return Math.PI * radius * radius * height;
    }

    @Override
    public String toString() {
        return "Cylinder: Surface Area = " + surface_area() + ", Volume = " + volume();
    }
}

4. Cone.java (Part 3)

public class Cone extends Shape {
    private double radius;
    private double height;

    public Cone(double radius, double height) {
        this.radius = radius;
        this.height = height;
    }

    @Override
    public double surface_area() {
        double slantHeight = Math.sqrt(radius * radius + height * height);
        return Math.PI * radius * (radius + slantHeight);
    }

    @Override
    public double volume() {
        return (1.0 / 3) * Math.PI * radius * radius * height;
    }

    @Override
    public String toString() {
        return "Cone: Surface Area = " + surface_area() + ", Volume = " + volume();
    }
}

5. ShapeArray.java (Part 4)

public class ShapeArray {
    public static void main(String[] args) {
        Shape[] shapeArray = new Shape[3];

        shapeArray[0] = new Sphere(5);
        shapeArray[1] = new Cylinder(3, 7);
        shapeArray[2] = new Cone(4, 9);

        for (Shape shape : shapeArray) {
            System.out.println(shape);
        }
    }
}
