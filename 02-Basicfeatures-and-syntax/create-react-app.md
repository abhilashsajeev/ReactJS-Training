## Setting up Project


### Using build workflows

#### why we need build workflows
- Optimize code (as minimal and ) since it increases the performance of our app
- **Use next gen JavaScript features** : Makes our life easier, add cross browser support
- **Be more productive**: CSS auto prefixing, ES6 features, linting

#### How we achieve this
- Use dependancy management tool like npm or yarn
- Use a bundler (Recommended by react: webpack). Webpack allows modifying the features of code in the middle way.
- Use a compiler (For next gen JavaScript features). We normally use Babel + Presets
- Use a development server

*Well this seems like super complex to setup!! Good thing is its not. Now let us see a tool that will create a project that will create a project that will create all these configurations out of the box. This is created by React community and is recommended way of building react applications.*

### Create react app

Create react app is created and maintained by react community around facebook. It is now the officially recommened way of creating reactjs applications.

Visit this [link to see official github repo](https://github.com/facebook/create-react-app)

Follow the instruction to install create react app.

We install it globally with npm
```
npm install -g create-react-app
```

_NB: in mac and linux you may need to prefix the above command with sudo_

#### Using create react app command
You can create a new reactjs app with following command
create-react-app <name-of-project>
```bash
//example
$ create-react-app myreactapp
```

myreactapp will be the folder gets generated were default configuration and starting files will be placed in.

Type `npm start` in terminal and it will start a development server in your local machine.

### Folder structure
- Let us see it in IDE.