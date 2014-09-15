#Javascript Quiz - Sept 15


##Questions

1. Make a `Person` constructor with attributes: `name:string`, `height:string`, `age:number`, `sleeping:boolean`.

```
function Person (name, height, age, sleeping){
  this.name = name;
  this.height = height;
  this.age = age;
  this.sleeping = true;
}

```

2. Add prototype methods to `person`: `eat`, `sleep`, and `wakeUp`. (The `sleep` and `wakeUp` methods should toggle `sleeping` to `true/false`, and `eat` should return an eating noise.)

```
Person.prototype.eat = function(){
  console.log("crunch... CRUNCH!");
};

Person.prototype.sleep = function(){
  this.sleeping = true;
};

Person.prototype.wakeUp = function(){
  this.sleeping = false;
};

```

3. Make a `Student` prototype that inherits from `person` and has the additional attribute of `studying:boolean`.

```
function Student (studying){
  this.studying = true;
}

Student.prototype = new Person();
Student.prototype.constructor = Student;

```

4. Add methods to `Student` called `study`, and `stopStudy` to toggle `studying`

```
Student.prototype.student = function(studying){

  this.study = function(studying){
    if (studying === false){
      this.studying = true;
    }
  };

  this.stopStudy = function(studying){
    if (studying === true){
      this.studying = false;
    }
  };
};

```

5. Override the `sleep` method on `student` to only run `sleep` if `studying` is `false`.

```
Student.prototype.sleep = function(studying){
  if (studying === false){
    this.sleep = true;
  } else {
    this.sleep = false;
  }
};

```