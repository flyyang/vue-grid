# vue-grid

> vue-grid with pagination


## Usage

If you aready use the vue-cli to build the project.Just copy `Table.vue` and `Pagination.vue` to your location. Import it and use it.

Used in the parent scope may like this:

```
 <template>
 <vue-grid :columns="gridOption.columns" :data="gridOption.data"></vue-grid>
 </template>
```

``` JavaScript
import VueGrid from './components/Table'

export default {
  components: {
    vueGrid: VueGrid
  },
  data: function () {
    return {
      gridOption: {
        columns: [
          {en: 'id', cn: '编号'},
          {en: 'domain', cn: '网址'},
          {en: 'user', cn: '邮箱'}
        ],
        data: [
          { id: 1, domain: 'google', user: 'test@github.com' }
					....
				]
			}
		}
	}
}
```
More details see the built step.

## Options

Note: option like `pageAble` must used with `page-able` in the custorm elments.

```
  <vue-grid :page-able="true"></vue-grid>
```

### data

* type: `Array`
* required: `true`
* default: []
* desc: the table's data that will be rendered.It requires below format:

```
[{'id':'1','name':'foo'},{id:'2',name:'bar'},{id: '3',name: 'baz'}]
```

It also suppot `html` in the field. Say if you want the name to `<span>foo</span>`,just format the data with the html.

### columns

* type: `Array`
* required: `true`
* desc: columns will be showed.Eg.:

```
[
  {en:'id',cn:'编号'},
  {en:'name',cn: '姓名'}
]
```
The `en` field used to extact data from the table data. The `cn` field used to specify the column's name(name in the <th> tag).

### pageSize

* type: `Number`
* default: 10

### checkAble

* type: `Boolean`
* default: flase
* description: wheter to show the checkbox in each `tr`

### checkedField

* type: `String`
* default: 'id'
* description: this option works with `checkAble` option. Say we have a data like this:
```
  [{'id':'1','name':'foo'},{id:'2',name:'bar'},{id: '3',name: 'baz'}]
```
If the checkedField is set to 'id', which is default, the id will be attached to the checkbox.

### checkedFields

* type: `Array`
* default: [],
* description: same with `checkedField`,but this option get all the checked `id` to this option. The checked option can find in the table `grid-select` property. Or you can set this to be sync with the parent componnet.

```
<vue-grid :checkedFields.sync="checkedFields"></vue-grid>
```

You can get checkedFields from the parent scope.

### searchAble

* type: `Boolean`
* default: `true`
* description: whether to show the search input

### pageAble

* type: `Boolean`
* default: `true`
* description: whether to show the pagination or not

### indexAble

* type: `Boolean`
* default: `false`
* description: whether to show the index or not

## Build Setup



``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```
