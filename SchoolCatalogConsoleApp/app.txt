class School {
  constructor (name, level, nOS){
    this._name = name;
    this._level = level;
    this._numberOfStudents = nOS;
  }
  get name () {
    return this._name;
  }
  get level () {
    return this._level;
  }
  get numberOfStudents () {
    return this._numberOfStudents;
  }
  set numberOfStudents (nNOS) {
    if(nNOS.isNaN){
      console.log('Invalid input: numberOfStudents must be set to a Number.');
    }else{
      this._numberOfStudents = nNOS;
    }  
  }
  quickFacts () {
    console.log(this._name+" educates "+this._numberOfStudents+" students at the "+this._level+" school level.")
  }
  static pickSubstituteTeacher (substituteTeachers) {
    const randomInt = Math.floor(Math.random()*substituteTeachers.length);
    return substituteTeachers[randomInt];
  }
};

class Primary extends School {
  constructor (name, nOS, pP) {
    super(name, "primary", nOS);
  	this._pickupPolicy = pP;
  }
  get pickupPolicy () {
    return this._pickupPolicy;
  }
};

class Middle extends School {
  constructor (name, nOS) {
    super(name, "middle", nOS);
  }
};

class High extends School {
  constructor (name, nOS, sportsTeams) {
    super(name, "high", nOS);
  	this._sportsTeams = sportsTeams;
  }
  get sportsTeams () {
    return this._sportsTeams;
  }
};


const lorraineHansbury = new Primary('Lorraine Hansbury', 1514, 'Students must be picked up by a parent, guardian, or a family member over the age of 13.');

lorraineHansbury.quickFacts();

School.pickSubstituteTeacher(['Jamal Crawford', 'Lou Williams', 'J. R. Smith', 'James Harden', 'Jason Terry', 'Manu Ginobli']);
console.log(School.pickSubstituteTeacher(['Jamal Crawford', 'Lou Williams', 'J. R. Smith', 'James Harden', 'Jason Terry', 'Manu Ginobli']));

const alSmith = new High('Al E. Smith', 2415, ['Baseball', 'Basketball', 'Volleyball', 'Track and Field']);
console.log(alSmith.sportsTeams);

alSmith.quickFacts();