# adoptaungato
pagina para adoptar animales  para personas con pocos recursos o traslados 
#laravel new adoptaungato
#php artisan make:auth
dentro del proyecto 
npm install
para ejecutar la compilacion 
npm run dev
para cambiar logo ingresar a app.blade
dentro de home  crear el dasboar 
pagina para iconos flaticon 
y  los fuente de agregan en app.scss 
@import url('https://fonts.googleapis.com/css?family=Open+Sans:400,700&display=swap');
y luego en variables.scss actualizar el fuente de open sans
para finalizar y ver los cambios agregar npm run dev
#php artisan make:model Profile -m  //m para las migraciones 
luego llenar los campos para las migraciones 
hacer la relacion  uno a uno con la tabla User 
ejemplo dentro de las migracion 
$table->unsignedBigInteger(user_id);
$table->index('user_id')
luego php artisan migrate 
como hacer una insert desde tinker
php artisan tinker
$profile=new \App\Profile();
$profile->title='Cool Title';
$profile->description='description';
$profile->user_id='1';
$profile->save();
#para acceder al valor de la tabla usuario ala tabla profiles 
{{$user->profiles->title}}
# ahora para crear el modelo pots para que los usuario puedan publicar  sus fotos con alguna descripcion 
php artisan make:model Posts -m  // m de migracion 
            $table->bigIncrements('id');
            $table->unsignedBigInteger('user_id');
            $table->string('caption'); 
            $table->string('image');
            $table->timestamps();

            $table->index('user_id');
luego hacemos la respectiva migracion 
php artisan migrate
php artisan migrate 

relaciones del modelo user 
public function posts(){
        return $this->hasMany(Post::class); // un usuario tiene muchas publicacioens 
    }
    public function profile(){
        return $this->hasOne(Profile::class); //un usuario tiene un solo perfil
    }
para hacer un rollback 
crear el controlador para el posts
php artisan make:controller PostsController
