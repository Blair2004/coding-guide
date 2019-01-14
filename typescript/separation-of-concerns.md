## The Separation of Concerns
building a large application require a good structure. Structing a code, is not only about creating subfolders where to places files, 
but to separate each file by their purpose. This is where the [separation of concerns is handy](https://en.wikipedia.org/wiki/Separation_of_concerns).
The purpose behing is to separate the script into "reusable" parts.

Assuming this Angular Component
```ts
@Component({
    /* ... */
})
UserComponent {

    userProfileForm: FormGroup;
    
    construct(
        private userService
    ){}
    
    /**
     * Proceed to a profile saving
     * @return void
    **/
    saveSettings() {
        // proceed to all the necessary validation here
        if ( /* whatever form is valid */ ) {
            this.userService.saveSettings( thsi.userProfileForm.value ).subscribe( response => {
                // do something with the response
            });
        }
    }
}
```

Assumming this user Service dependency
```ts
@Injectable()
class userService {
    constructor( 
        private http: HttpClient
    ){}
    
    /**
     * save settings of the logged user
     * @param object form value
     * @return observable
    **/
    saveSettings( fields: ProfileFields ): Observable<AsyncResponse> {
        return this.http.post( 'http://fakeapi.com/user/profile', fields );
    }
}
```

As you can notice, we've stored the service into another file. Doing that make the service "reusable". 
it can be used by another component
