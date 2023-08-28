# Async

async function  - is an asyncrounus function

try{}catch(error){console.error(error)}  - do the try, if an error break out and do catch

let bananna = new Promise((resolve, reject) =>{
    resolve()   or    reject()
})

await bananna    - wait for the resolve then immediatly do code underneath


const response = await fetch(URL)