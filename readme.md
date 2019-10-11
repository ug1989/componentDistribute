// index.html
<script src=main.js></script>

// main.js
import react from 'cdn#react@3.0';

import reactDom from 'cdn#react-dom@2.0.2';

import { Provider } from 'cdn@redux@2.2.1';


import Store from 'cdn@store@1.0.0';

import Index from './Index.jsx';


reactDom.render(<Provider store={store}><Index></Provider>, document.querySeleter('#app'));

// store.js
import { createStore, applyMiddleware } from 'cdn@redux@2.2.1';

const initStore = {};

const asyncReducer = {};

let store;


export function injectReducer(reduces) {

  store.replaceReducer(createReducer(asyncReducer, store.getState()));

}


export default store = createStore(createReducer(), initialState, applyMiddleware());

// Index.jsx
import react from 'cdn#react@3.0';

import reactDom from 'cdn#react-dom@2.0.2';


import Switch from 'cpm#Switch@1.0.1';

import ItemCpn from 'cpm#Item@1.8.5';

import ItemLocal from './Item.jsx';


export default class Index extends react.Component {

  constructor() {

    this.state = {};
 
  }
  
  
  render() {
  
    <div calss="header"></div>
    
      <div calss="content">
      
        <Switch>
        
          <ItemCpn />
          
            <ItemLocal />
  
        </Switch>
   
      </div>
    
    <div calss="footer"></div>

  }

}


/**　构架说明　**/
- 基于统一技术栈 react、react-router、redux
- 异步注入reducer(共享reducer在store中初始化绑定，后续加载页面或模块自建子状态)
- 资源独立部署，cdn(基础库，分版本) | cpm(组件库，分版本、分环境)

- 子项目或独立组件使用统一的模块加载配置，共用资源

- 服务端配置http2.0，减少零散资源加载消耗

- 创建全局的资源管理表及状态流程图，构建过程中输出依赖及关联关系，便于测试覆盖
