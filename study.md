1. Vue CLI : https://cli.vuejs.org/
sudo -i
npm install -g @vue/cli 

vue create hello-world or vue create .
npm run serve

2. template error | jsconfig.json:
"jsx": "preserve",

3. naming error: use HeaderMain in stead of Header

4. Bootstrap
npm i bootstrap@5.2.1
npm i jquery popper.js

main.js
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';

5. HTTP Request Using Vue Resource
npm install vue-resource
https://github.com/pagekit/vue-resource

6. vite
npm create vite@latest

7. axios
npm install axios

8. JSONPlaceholder https://jsonplaceholder.typicode.com/

9. composition api: another way to write components in vue (everything inside setup() method)
optional api: data, methods, computed properties, watchers, lifecycle hooks

10. lodash
npm install lodash

11. vue-cli-service: Permission denied

rm -rf node_modules/
npm install