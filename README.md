# github-profile-wrapper
<h6>showing data or output of data  18:00</h6>
const userNameInput  = document.getElementById('userName');
const showDetailsButton = document.getElementById('showDetails');

showDetailsButton.addEventListener('click', () =>{
    const userName  = userNameInput.value;
  
    //request  the data frm server: fetch api
  //fetch(`https://api.github.com/users/${userName}`)
  fetch(`https://api.github.com/users/${userName}`)
    .then((res)=> res.json())
    .then((data) => console.log(data))
     
})

Vishal-raj-1

<h5>showing names on screen</h5>

const userNameInput  = document.getElementById('userName');
const showDetailsButton = document.getElementById('showDetails');
const profileInfoDiv = document.getElementById('profileInfo');

showDetailsButton.addEventListener('click', () =>{
    const userName  = userNameInput.value;
  
    //request  the data frm server: fetch api
  //fetch(`https://api.github.com/users/${userName}`)
  fetch(`https://api.github.com/users/${userName}`)
    .then((res)=> res.json())
    .then((data) => {
      console.log(data);
      profileInfoDiv.innerHTML = `<div class="card">
     <div class="card-img">
           <img src="${data.avatar_url}" alt=${data.name}>        
    </div>
     <div class="card-body">
            <div class="card-title">${data.name}</div>
            <div class="card-subHeading">${data.login}
            </div>
      <div class="card-text">
         <p>${data.bio}</p>
         <p>${data.followers}   followers ${data.following}  following</p>
         <p>${data.id}</p>
      </div>
      </div>
 </div>`
     
    })
}) 


///////////////////////////////////
<h5>html code</h5><!DOCTYPE html>
///////////////////////////////////
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Wrapper</title>
    <link rel="stylesheet" href="githubwrapper.css">
</head>
<body>
    <div class="container">
        <div class="main">
            <h1>Github Profile Wrapper</h1>
            <input type="text" id="userName" placeholder="Github Username">
            <button id="showDetails">Show Details</button>
        </div>

          <div id="profileInfo">
           
          </div>
        </div>
        <script src="githubwrapper.js"></script>
    </body>
    </html>


<h3>promises from  vishal rajput</h3>
  // promise, resolve, reject, pending
// const p = new Promise((resolve, reject) => {
//   const x = 1 + 1;
//   if(x == 2){
//     resolve('success');
//   } else {
//     reject('Failed');
//   }
// })

// //then will be executed when promise resovle , otherwise catch will be executed

// p.then((data) => console.log(data)).catch((err) => console.log(err))




<h4>repositery code js </h4>
const userNameInput  = document.getElementById('userName');
const showDetailsButton = document.getElementById('showDetails');
const profileInfoDiv = document.getElementById('profileInfo');

function showRepoInfo(userName){
    fetch(`https://api.github.com/users/${userName}/repos`)
       .then(res => res.json())
       .then(data => console.log(data))
}
showDetailsButton.addEventListener('click', () =>{
    const userName  = userNameInput.value;
  
    //request  the data frm server: fetch api
  //fetch(`https://api.github.com/users/${userName}`)
  fetch(`https://api.github.com/users/${userName}`)
    .then((res)=> res.json())
    .then((data) => {
      // console.log(data);            ///////////////////////   yha comment kr diya to data print nhi hoga jo phle sb hota tha name, follwer,... ab only repo ka data sho kreg bs
      profileInfoDiv.innerHTML = `<div class="card">
     <div class="card-img">
           <img src="${data.avatar_url}" alt=${data.name}>        
    </div>
     <div class="card-body">
            <div class="card-title">${data.name}</div>
            <div class="card-subHeading">${data.login}
            </div>
      <div class="card-text">
         <p>${data.bio}</p>
         <p>${data.followers}   followers ${data.following}  following</p>
         <p>${data.id}</p>
      </div>
      </div>
 </div>`

 
/////////////////////////////////////////
 <h5>creating cards for projects</h5>
 ////////////////////////////////////////
js code

 const userNameInput  = document.getElementById('userName');
const showDetailsButton = document.getElementById('showDetails');
const profileInfoDiv = document.getElementById('profileInfo');
const reposInfoDiv =  document.getElementById('reposInfo')

function showRepoInfo(userName){
    fetch(`https://api.github.com/users/${userName}/repos`)
       .then(res => res.json())
       .then(projects =>{
        console.log(projects);
        for(let i=0; i<projects.length; i++){
          reposInfoDiv.innerHTML += `<div class="card">       
         </div
          <div class="card-body">
                 <div class="card-title">${projects[i].name}</div>
                 <div class="card-subHeading">${projects[i].language}
                 </div>
           <div class="card-text">
                 <button>
                 <a href=${projects[i].html_url}>
                    Do checkout Project
                    </a>
                 </button>
                 
           </div>
           </div>
      </div>`
           }
       })
}
showDetailsButton.addEventListener('click', () =>{
    const userName  = userNameInput.value;
  
    //request  the data frm server: fetch api
  //fetch(`https://api.github.com/users/${userName}`)
  fetch(`https://api.github.com/users/${userName}`)
    .then((res)=> res.json())
    .then((data) => {
      // console.log(data);
      profileInfoDiv.innerHTML = `<div class="card">
     <div class="card-img">
           <img src="${data.avatar_url}" alt=${data.name}>        
    </div>
     <div class="card-body">
            <div class="card-title">${data.name}</div>
            <div class="card-subHeading">${data.login}
            </div>
      <div class="card-text">
         <p>${data.bio}</p>
         <p>${data.followers}   followers ${data.following}  following</p>
         <p>${data.id}</p>

         <button>
         <a href=${data.html_url}>
            Do checkout Profile
            </a>
         </button>
      </div>
      </div>
 </div>`
      

          
            showRepoInfo(userName);
    })
}) 

////////////////// html code ////////////////////////////////////////////////////////////////////////////////// in creating cards for projects//////////////////

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Wrapper</title>
    <link rel="stylesheet" href="githubwrapper.css">
</head>
<body>
    <div class="container">
        <div class="main">
            <h1>Github Profile Wrapper</h1>
            <input type="text" id="userName" placeholder="Github Username">
            <button id="showDetails">Show Details</button>
        </div>

          <div id="profileInfo">
          </div>
           
          <div id="reposInfo">

          </div>

        </div>
        <script src="githubwrapper.js"></script>
    </body>
    </html>
//////////////////////////////////////
use of async awit why////////////////////////////////////////////////////////////////////
///////////////////////////////////
note:- promise resolve krne ke liye .then ka use kr rhe .then krne ke baad fir se promise a jaaa rha hai to fir se promise ko remove krnek re liye .then ka use kr rhe hai.
  // promise, resolve, reject, pending
// const p = new Promise((resolve, reject) => {
//   const x = 1 + 1;
//   if(x == 2){
//     resolve('success');  
//   } else {
//     reject('Failed');
//   }
// })

// //then will be executed when promise resovle , otherwise catch will be executed

// p.then((data) => console.log(data)).catch((err) => console.log(err))   // here return  promise
//if p.then use again and return promise then use of async await// and promise returning again and again is call long chaining

// fetch(`https://api.github.com/users/${userName}/repos`)    retured promise 
//        .then(res => res.json())                            use then to resolve promise
//        .then(projects =>{                           again returned promise then used then to resolve promise
  // same as then and catch we use async and await
