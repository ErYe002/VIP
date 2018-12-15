import React from "react"
import {Link} from "react-router-dom"
import {Segment,Menu,Image} from "semantic-ui-react"
import {connect} from "react-redux"

class Page1 extends React.Component{
    constructor(props){
        super(props)
        this.state={
            mes:"",
            name:"李三岁"
        }
    }
    render(){
        let {text,color,colors} = this.props;
        return(
            <div>
                    <Segment 
                        style={{
                            textAlign:'center',width:'60%',margin:'10px auto'
                        }}>
                        长恨歌-{this.state.name}
                    </Segment>
                    <Segment 
                        style={{
                            textAlign:'center',margin:'10px auto'
                        }}>
                        汉皇重色思倾国，御宇多年求不得。<br/>
                        杨家有女初长成，养在深闺人未识。<br/>
                        天生丽质难自弃，一朝选在君王侧。<br/>
                        回眸一笑百媚生，六宫粉黛无颜色。<br/>
                        春寒赐浴华清池，温泉水滑洗凝脂。<br/>
                        侍儿扶起娇无力，始是新承恩泽时。<br/>
                    </Segment>
                    <div>
                        <p style={{color:colors}}>{text}</p>
                        <button onClick={color}>按这</button>
                    </div>
                </div>

        )
    }
}
const mapStateToProps = (state) => {
    return {
        text: state.text,
        colors:state.color
    }
}

const mapDispatchToProps = (dispatch) => {
    return {
        color() {
            let action = {
                type: "colorChange",
                color:"red"
            }
            dispatch(action);
        }
    }
}

export default connect(mapStateToProps,mapDispatchToProps)(Page1);
