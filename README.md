# divamiTechnicalTestQuestion  

1) first question
const data = [
  [
    { id: "a1", value: 10 },
    { id: "a2", value: 20 },
    { id: "a3", value: 30 },
    { id: "a4", value: 40 },
    { id: "a5", value: 50 }
  ]
];  


const result = data[0].map(item => `"${item.id}" : ${item.value}`).join(",")

console.log(result)   


2) question

using for loop ;
Question:
"Given an object representing a person with nested contact information, write a function to fetch all the values within this object into a flat array."


const person = {
  name: "John",
  contact: {
    phone: "987-654-3210",
    email: "john123@xyz.com",
    address: {
      city: "Berlin",
      country: "Germany"
    }
  }
};

function getValueArray(obj){
  const stack = [obj] 
  const result = [];
  
  while (stack.length > 0){
    const current = stack.pop(); 
    
    for(const key in current){
    
      if(typeof current[key] === 'object' && current[key] !== null){
        stack.push(current[key])
        
      }else{
        result.push(current[key])
        
      }
    }
  }
  
  
  return result
}


const flatValue = getValueArray(person); 
console.log(flatValue);


recursive 


const person = {
  name: "John",
  contact: {
    phone: "987-654-3210",
    email: "john123@xyz.com",
    address: {
      city: "Berlin",
      country: "Germany"
    }
  }
};

function getValueArray(obj){
  const result = []; 
  
  function recursive(currentObj){
    for(const key in currentObj){
      if(typeof currentObj[key] === 'object' && currentObj[key] !== null){
        recursive(currentObj[key])
      }else{
        result.push(currentObj[key])
      }
    }
  }
  recursive(obj)
  return result
  }
  
const flatValue = getValueArray(person); 
console.log(flatValue);




