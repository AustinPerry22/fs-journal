# Async

async function  - is an asyncrounus function

try{}catch(error){console.error(error)}  - do the try, if an error break out and do catch

let banana = new Promise((resolve, reject) =>{
    resolve()   or    reject()
})

await banana    - wait for the resolve then immediatly do code underneath


const response = await fetch(URL)

create read update delete - CRUD methods

async func{
    try{
        do stuff
        await thing im requesting
    }
    catch(error){
        pop error
    }
}

static exists on the class iteslf not on each instance

