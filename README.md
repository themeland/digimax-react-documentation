# Template customization


## public
I hope you have seen this template `public` folder on the downloaded package `Digimax - React SEO & Digital Marketing Agency Template` from ThemeForest.

In this `public` folder you can see `index.html` file. This file structure is like this-

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!--meta, title, google fonts, all css linking here-->
</head>

<body>

  <div id="root"></div>
 
 <!--all js linking here-->
</body>

</html>
```

All HTML content will be load into this `div`:
```html
<div id="root"></div>
```




## entry points

##### index.js
Template `index.js` structure looks like this-
```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

```

##### app.js
Template `app.js` structure looks like this-
```js
import React from 'react';

// importing MyRouts where we located all of our theme
import MyRouts from './routers/routes'

function App() {
  return (
    <div>
      <MyRouts />
    </div>
  );
}

export default App;

```


## themes

`themes` folder included on `src` folder. You can check our folder structure on `src` folder menu.
This is `theme` folder structure-
```text
|-- themes
    |-- theme-one.js ( default theme)
    |-- theme-two.js ( demo theme 2)
    .....
    |-- theme-twelve.js ( demo theme 12 )
```

`theme` folder contains all of our 12 demos.


## routes
In `routers` folder we used `routes.js`. Where we linked all the route for our all theme. For routing we used react-router-dom.

Routes: `routers/routes.js`

```js
import React from "react";
import { BrowserRouter as Router, Route, Switch } from "react-router-dom";

// importing all the themes
import ThemeOne from "../themes/theme-one";
import ThemeTwo from "../themes/theme-two";
import ThemeThree from "../themes/theme-three";
import ThemeFour from "../themes/theme-four";
import ThemeFive from "../themes/theme-five";
import ThemeSix from "../themes/theme-six";
import ThemeSeven from "../themes/theme-seven";
import ThemeEight from "../themes/theme-eight";
import ThemeNine from "../themes/theme-nine";
import ThemeTen from "../themes/theme-ten";
import ThemeEleven from "../themes/theme-eleven";
import ThemeTwelve from "../themes/theme-twelve";
import About from "../components/InnerPages/About/About";
import Services from "../components/InnerPages/Services/Services";
import PortfolioGrid from "../components/InnerPages/Portfolio/PortfolioGrid/PortfolioGrid";
import PortfolioMinimal from "../components/InnerPages/Portfolio/PortfolioMinimal/PortfolioMinimal";
import PortfolioNoGap from "../components/InnerPages/Portfolio/PortfolioNoGap/PortfolioNoGap";
import PortfolioMasonry from "../components/InnerPages/Portfolio/PortfolioMasonry/PortfolioMasonry";
import Team from "../components/InnerPages/Team/Team";
import Pricing from "../components/InnerPages/Pricing/Pricing";
import Contact from "../components/InnerPages/Contact/Contact";
import Error from "../components/InnerPages/Error/Error";
import BlogTwoColumn from "../components/Blogs/BlogTwoColumn";
import BlogThreeColumn from "../components/Blogs/BlogThreeColumn";
import BlogLeftSidebar from "../components/Blogs/BlogLeftSidebar";
import BlogRightSidebar from "../components/Blogs/BlogRightSidebar";
import BlogDetailsLeftSidebar from "../components/Blogs/BlogDetailsLeftSidebar";
import BlogDetailsRightSidebar from "../components/Blogs/BlogDetailsRightSidebar";

class MyRouts extends React.Component {
  render() {
    return (
      <div>
        <Router>
          <Switch>
            <Route exact path="/" component={ThemeOne} />
            <Route exact path="/theme-two" component={ThemeTwo} />
            <Route exact path="/theme-three" component={ThemeThree} />
            <Route exact path="/theme-four" component={ThemeFour} />
            <Route exact path="/theme-five" component={ThemeFive} />
            <Route exact path="/theme-six" component={ThemeSix} />
            <Route exact path="/theme-seven" component={ThemeSeven} />
            <Route exact path="/theme-eight" component={ThemeEight} />
            <Route exact path="/theme-nine" component={ThemeNine} />
            <Route exact path="/theme-ten" component={ThemeTen} />
            <Route exact path="/theme-eleven" component={ThemeEleven} />
            <Route exact path="/theme-twelve" component={ThemeTwelve} />
            <Route exact path="/about" component={About} />
            <Route exact path="/services" component={Services} />
            <Route exact path="/portfolio-grid" component={PortfolioGrid} />
            <Route exact path="/portfolio-minimal" component={PortfolioMinimal} />
            <Route exact path="/portfolio-no-gap" component={PortfolioNoGap} />
            <Route exact path="/portfolio-masonry" component={PortfolioMasonry} />
            <Route exact path="/team" component={Team} />
            <Route exact path="/pricing" component={Pricing} />
            <Route exact path="/contact" component={Contact} />
            <Route exact path="/404" component={Error} />
            <Route exact path="/blog-two-column" component={BlogTwoColumn} />
            <Route exact path="/blog-three-column" component={BlogThreeColumn} />
            <Route exact path="/blog-left-sidebar" component={BlogLeftSidebar} />
            <Route exact path="/blog-right-sidebar" component={BlogRightSidebar} />
            <Route exact path="/blog-details-left-sidebar" component={BlogDetailsLeftSidebar} />
            <Route exact path="/blog-details-right-sidebar" component={BlogDetailsRightSidebar} />
          </Switch>
        </Router>
      </div>
    );
  }
}
export default MyRouts;

```


## components
Under `components` folder we wrote all of our components individually. 
We have written these components to make the developer’s life easy. 
By using these basic components, For example in our components directory there is `Header`, `Hero` , `Footer` folder where we wrote our different styled component. For example `Hero` component-

### Component folder structure
```text
|-- components
    ....
    |-- Hero ( hero component folder )
        - HeroOne.js ( main demo hero section )
        - HeroTwo.js ( demo two hero section )
        ...... ( and other )
        
    |-- Contact ( contact folder )
        - ContactOne.js 
        - ContactTwo.js
        - ContactThree.js
    .
    ..
    ...    
```

### Contact Section component
`Contact/ContactOne.js`
```js
import React, { Component } from 'react';
import axios from 'axios';

const BASE_URL = "https://my-json-server.typicode.com/themeland/digimax-json-1/themeOneContactSection";

class ContactOne extends Component {
    state = {
        data: {},
        contactData: []
    }
    componentDidMount(){
        axios.get(`${BASE_URL}`)
            .then(res => {
                this.setState({
                    data: res.data,
                    contactData: res.data.contactData
                })
                // console.log(this.state.data)
            })
        .catch(err => console.log(err))
    }
    render() {
        return (
            <section id="contact" className="contact-area ptb_100">
                <div className="container">
                    <div className="row justify-content-between align-items-center">
                        <div className="col-12 col-lg-5">
                            {/* Section Heading */}
                            <div className="section-heading text-center mb-3">
                                <h2>{this.state.data.heading}</h2>
                                <p className="d-none d-sm-block mt-4">{this.state.data.headingText_1}</p>
                                <p className="d-block d-sm-none mt-4">{this.state.data.headingText_2}</p>
                            </div>
                            {/* Contact Us */}
                            <div className="contact-us">
                                <ul>
                                    {/* Contact Info */}
                                    {this.state.contactData.map((item, idx) => {
                                        return(
                                            <li key={`co_${idx}`} className={item.listClass}>
                                                <span><i className={item.iconClass} /></span>
                                                <a className={item.linkClass} href="/#">
                                                    <h3>{item.title}</h3>
                                                </a>
                                                <p>{item.text}</p>
                                            </li>
                                        );
                                    })}
                                </ul>
                            </div>
                        </div>
                        <div className="col-12 col-lg-6 pt-4 pt-lg-0">
                            {/* Contact Box */}
                            <div className="contact-box text-center">
                                {/* Contact Form */}
                                <form id="contact-form" method="POST" action="/php/mail.php">
                                    <div className="row">
                                        <div className="col-12">
                                            <div className="form-group">
                                                <input type="text" className="form-control" name="name" placeholder="Name" required="required" />
                                            </div>
                                            <div className="form-group">
                                                <input type="text" className="form-control" name="name" placeholder="Company Name" required="required" />
                                            </div>
                                            <div className="form-group">
                                                <input type="email" className="form-control" name="email" placeholder="Email" required="required" />
                                            </div>
                                            <div className="form-group">
                                                <input type="text" className="form-control" name="subject" placeholder="Phone" required="required" />
                                            </div>
                                        </div>
                                        <div className="col-12">
                                            <div className="form-group">
                                                <textarea className="form-control" name="message" placeholder="Message" required="required" defaultValue={""} />
                                            </div>
                                        </div>
                                        <div className="col-12">
                                            <button type="submit" className="btn btn-bordered active btn-block mt-3"><span className="text-white pr-3"><i className="fas fa-paper-plane" /></span>{this.state.data.btnText}</button>
                                        </div>
                                    </div>
                                </form>
                                <p className="form-message" />
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        );
    }
}

export default ContactOne;
```

### Footer Section component
`Footer/FooterOne.js`
```js
import React, { Component } from 'react';
import axios from 'axios';

const BASE_URL = "https://my-json-server.typicode.com/themeland/digimax-json-2/themeOneFooterSection";

class FooterOne extends Component {
    state = {
        data: {},
        footerList_1: [],
        footerList_2: [],
        footerList_3: [],
        iconList: []
    }
    componentDidMount(){
        axios.get(`${BASE_URL}`)
            .then(res => {
                this.setState({
                    data: res.data,
                    footerList_1: res.data.footerList_1,
                    footerList_2: res.data.footerList_2,
                    footerList_3: res.data.footerList_3,
                    iconList: res.data.iconList
                })
                // console.log(this.state.data)
            })
        .catch(err => console.log(err))
    }
    render() {
        return (
            <footer className="section footer-area">
                {/* Footer Top */}
                <div className="footer-top ptb_100">
                    <div className="container">
                        <div className="row">
                            <div className="col-12 col-sm-6 col-lg-3">
                                {/* Footer Items */}
                                <div className="footer-items">
                                    {/* Footer Title */}
                                    <h3 className="footer-title text-uppercase mb-2">{this.state.data.footerTitle_1}</h3>
                                    <ul>
                                        {this.state.footerList_1.map((item, idx) => {
                                            return(
                                                <li key={`flo_${idx}`} className="py-2"><a className="text-black-50" href="/#">{item.text}</a></li>
                                            );
                                        })}
                                    </ul>
                                </div>
                            </div>
                            <div className="col-12 col-sm-6 col-lg-3">
                                {/* Footer Items */}
                                <div className="footer-items">
                                    {/* Footer Title */}
                                    <h3 className="footer-title text-uppercase mb-2">{this.state.data.footerTitle_2}</h3>
                                    <ul>
                                        {this.state.footerList_2.map((item, idx) => {
                                            return(
                                                <li key={`flt_${idx}`} className="py-2"><a className="text-black-50" href="/#">{item.text}</a></li>
                                            );
                                        })}
                                    </ul>
                                </div>
                            </div>
                            <div className="col-12 col-sm-6 col-lg-3">
                                {/* Footer Items */}
                                <div className="footer-items">
                                    {/* Footer Title */}
                                    <h3 className="footer-title text-uppercase mb-2">{this.state.data.footerTitle_3}</h3>
                                    <ul>
                                        {this.state.footerList_3.map((item, idx) => {
                                            return(
                                                <li key={`flth_${idx}`} className="py-2"><a className="text-black-50" href="/#">{item.text}</a></li>
                                            );
                                        })}
                                    </ul>
                                </div>
                            </div>
                            <div className="col-12 col-sm-6 col-lg-3">
                                {/* Footer Items */}
                                <div className="footer-items">
                                    {/* Footer Title */}
                                    <h3 className="footer-title text-uppercase mb-2">{this.state.data.footerTitle_4}</h3>
                                    <p className="mb-2">{this.state.data.text}</p>
                                    {/* Social Icons */}
                                    <ul className="social-icons list-inline pt-2">
                                        {this.state.iconList.map((item, idx) => {
                                            return(
                                                <li key={`fi_${idx}`} className="list-inline-item px-1"><a href="/#"><i className={item.iconClass} /></a></li>
                                            );
                                        })}
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                {/* Footer Bottom */}
                <div className="footer-bottom bg-grey">
                    <div className="container">
                        <div className="row">
                            <div className="col-12">
                                {/* Copyright Area */}
                                <div className="copyright-area d-flex flex-wrap justify-content-center justify-content-sm-between text-center py-4">
                                    {/* Copyright Left */}
                                    <div className="copyright-left">© Copyrights 2020 Digimax All rights reserved.</div>
                                    {/* Copyright Right */}
                                    <div className="copyright-right">Made with <i className="fas fa-heart" /> By <a href="/#">Themeland</a></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </footer>
        );
    }
}

export default FooterOne;
```


## theme installtion
To install the theme you have to install [react](https://create-react-app.dev/) than go to the theme root dir where `package.json` located and use
```bash
npm install
```
it will install the packages.

After install process now you can run local server- local server port is 'http://localhost:3000' For developement start use
```bash
npm start
```
## Build your theme
```bash
npm run build
```

## For deployment -- static server
First install
```bash
npm install -g serve
serve -s build
```
If you want to know more about static deployment please visit [Create react app deployment](https://create-react-app.dev/docs/deployment)

Enjoy your theme :)
