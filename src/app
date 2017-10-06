import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';



var platform = {
  user:{
    unique_id : 91,
    favorites_id : [1,2,3,4,5,6,7,8,9]
    },
  video_id: [2,5,6,7,9,10,11,12,13,14,15,20,22,24]
}


function favToggle(props){
  var videoNumber = props.video_id
  var array = props.favoritesList
  if(array.includes(videoNumber)){
    array.splice(array.indexOf(videoNumber),1)
  } else{
    array.push(videoNumber)
  }
}

class Toggle extends Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: this.props.isToggleOn};
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    favToggle(this.props);
    this.setState(prevState => ({
      isToggleOn: !prevState.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'Favorite' : 'Unfavorite'}
      </button>
    );
  }
}

function Match(props){
  var favoritesList = props.favoritesList
  var videoNumber = props.videoId
  if(favoritesList.includes(videoNumber)){
    return(
      <div>This Video is in your favorites!<br/>Remove From Favorites: 
      < Toggle isToggleOn={false} favoritesList={favoritesList} video_id={videoNumber}/><br/><br/></div>
    );
  } else {
    return(
      <div>This Video is not in your favorites!<br/>Make Favorite: 
      < Toggle isToggleOn={true} favoritesList={favoritesList} video_id={videoNumber} /><br/><br/></div>
    );
  }
}

function VideoContent(props){
  var videos = props.videos.video_id
      return(
        <div>
        {videos.map((item, index) => (
           <div className='video' key={index} id={item}>
           Videos unique id:{item}
           < Match favoritesList={props.videos.user.favorites_id} videoId={item}/>
           </div>
        ))}
       </div>
      );
}

class Video extends Component {
  render(){
    return (
      <div className="Video-content"> 
        Video would be contained here<br/><br/>
        < VideoContent videos={platform} />
      </div>
    )
  }
}


class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
        < Video/>
      </div>
    );
  }
}

export default App;
