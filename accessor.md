# `@Accessor`

[<- Return](README.md)

Sets or gets a target field.

Parameters:

 - Setter: Target field's type
 - Getter: No parameters

Return type:

 - Setter: `void`
 - Getter: Target field's type

**Must be done in an interface**

Example mixin:
```java
@Mixin(Dummy.class)
public interface AccessorMixin {
	@Accessor("dummyField")
	int getDummyField();

	@Accessor("dummyField")
	void setDummyField(int value);
}
```
```kt
@Mixin(Dummy::class)
public interface AccessorMixin {
	@Accessor(["dummyField"])
	getDummyField(): Int

	@Accessor(["dummyField"])
	setDummyField(value: Int)
}
```

Usage:

```java
  public void myMethod() {
  	// Getting the field
      	int i = ((AccessorMixin) Dummy.getInstance()).getDummyField();

      	// Setting the field
      	((AccessorMixin) Dummy.getInstance()).setDummyField(i + 1);
  }
```
```kt
  public myMethod() {
      	// Getting the field
      	(Dummy.getInstance() as AccessorMixin).dummyField += 1 // Setting the field
  }
```
