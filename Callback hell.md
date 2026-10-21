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




```
