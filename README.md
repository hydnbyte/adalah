composer create-project laravel/laravel:^12.0 perpus

Schema::create('users', function (Blueprint $table) {
            $table->id();
            $table->integer('school_id')->unsigned();
            $table->string('name');
            $table->string('class');
            $table->string('major');
            $table->string('username')->unique();
            $table->enum('role', ['admin','member'])->default('member');
            $table->string('password');
            $table->string('email')->unique();
            $table->timestamp('email_verified_at')->nullable();
            $table->rememberToken();
            $table->timestamps();
        });

php artisan make:seeder AdminSeeder 

php artisan db:seed --class=AdminSeeder
