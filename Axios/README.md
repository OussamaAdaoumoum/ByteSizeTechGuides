histroy:
(9bel flweb makantch endna chi haja asynchrone, kan taikhesna dima n3awdo nrechargiw la page bach njibo les donnnees), and with time evolution we really needed to pass to the asynchronisation, and here the XMLHttpRequest has been founded, and to work with it, we have to rewrite the same code every time(boilerplate) and that was not really good.

after this fetch api was founded to replace the work that we have to do with XHR
after fetsh API axios has been founded 


comparing:
    - fetshApi: we dont need to download it, because we have it by default in the javascript engine our browsers, and it is more lightweight comparing to the other tools 

    - axios: we can define the endpoints / configure by default values, ...
            he is working with xsrf to protect the request.
            axios can analyse the response status, and he can know if it is ok or not (200 ok/ 404 error ...).
            by default data returned is json, comapring with fetch we have to transform the respons to json manually
            we can also cancel a request when we sending it.
            when we want to send data we sending it as json, comparing to fetsh where wo have to return it to a string so we can to send it.
            with axios we can use the progress bar to stimulate the upload of a file for example (we can use this with fetsh)
            axios based on XHR, so we can use in in both front and backend

should i work with axios or fetsh api ?
whenever you want to work with axios, you have to ask yourself this question, im i needing all this fetures provided with axios or not?, because if you won't use all his features, you really don't want to add a whole package to your application, to the some operations that you can done juste by using fetsh api, because like we sayd fetsh api is more lightweight that axios, and adding axios to your project means adding more things that can really slow your project.

fetsh api examples :

* with axios we can set the timeout of a request, after this timeout, the request is cancelled (in this case axios is based on the aboart controller)
* CustomAxios, we can create a custom axios configuration ( give the url, timeout, .....)
* simultaneous requests with axios / and also when we have some data that is importent to be fetshed in one time without waithing for other requests (we use Promise.all(), or axios.all()) / spread operator when we fetch
* Axios request/response interceptors (we use it when we want to show something in the time of sending a request or receiving it )
* customise the request, example:  CustomAxios.defaults.headers.get['Authorization']='dada'


Http verb (request methodes in axios ), how to use in in fetsh, and compare it to axios

