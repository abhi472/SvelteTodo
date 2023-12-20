  
    <p></p>
    <button on:click={addTrack}>click</button>
    
    <p>
        Album length is {albumLength.minutes} minutes and {albumLength.seconds} seconds
    </p>
<script>
    let album = [
        {track: 'Track 1', length: 100},
        {track: 'Track 2', length: 200},
        {track: 'Track 3', length: 300},
    ]
    
    /**
     *  $ sign tells that the variable is reactive, 
     * i.e. it observes changes to its source and emits the result
     */
    $: albumLength = getAlbumLength(album);
    
    function getAlbumLength(album) {
        let lengthSeconds = album.reduce (
            (a,b) => {
                return a+b.length;
            }, 0);
    
            let [minutes, seconds] = (lengthSeconds/60)
            .toFixed(2)
            .toString()
            .split('.');
            return {minutes,seconds}
        
    }
     
    function addTrack() {
    
        album = [...album, {track: 'Track 4', length: 200}];
    
    }
    
    
    
    
    </script>
  
    