```javascript
function getData(dataId, getNextData) {
  setTimeout(() => {
    console.log("data ", dataId);
    if (getNextData) {
      getNextData();
    }
  }, 4000);
}

//callback hell
getData(1, () => {
  console.log("getting data 2...");
  getData(2, () => {
    console.log("getting data 3...");
    getData(3, () => {
      console.log("getting data 4...");
      getData(4);
    });
  });
});


//basic promise
const getPromise = () => {
  return new Promise((res, rej) => {
    console.log("I am promise");
    rej("Success");
  });
};

let promise = getPromise();
promise.then((res) => {
  console.log("Promise fulfilled");
});

promise.catch((err) => {
  console.log("Promise Failed", err);
});

//promise chaining
function asynFunc() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Data1");
      resolve("Success");
    }, 5000);
  });
}

function asynFunc2() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Data2");
      resolve("Success");
    }, 5000);
  });
}

console.log("fetching data1...");
let p1 = asynFunc();
p1.then((res) => {
  console.log(res);
  console.log("fetching data2...");
  let p2 = asynFunc2();
  p2.then((res) => {
    console.log(res);
  });
});










```
