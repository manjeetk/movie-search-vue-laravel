
# Movie search application using Vue JS and Laravel framework using OMDb API - The Open Movie Database
 
 A laravel movie search application using Vue JS, Vue Composition API
 and OMDBAI API.
 OMDBAI is used to fetch the movies data from https://www.omdbapi.com/

## Requirements

	- **Composer 2.0.13**
	- **Node version v14.17.0**
	- **PHP version 8.0.3** 
 
## Installation
	- **composer create-project laravel/laravel movie-search**
	- **cd movie-search**
	- **composer require laravel/ui**
	- **php artisan ui vue**
	- **npm install vue-loader@^15.9.5 --save-dev --legacy-peer-deps**
	- **npm install @vue/composition-api**
    - **npm install -D @babel/core @babel/preset-env babel-loader**
	- **npm install**
	- **npm run dev**
	- **npm run watch**

## Update you API key from the [OMDb API](https://www.omdbapi.com/) in /resources/js/components/movieapi/movie-api.js file

	```js
    import { reactive, watch } from '@vue/composition-api';
	const API_KEY = '######';
    ```
