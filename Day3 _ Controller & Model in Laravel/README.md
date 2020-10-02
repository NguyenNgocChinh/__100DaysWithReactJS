# CONTROLLER
* Cấu trúc một Controller:

      <?php

      namespace App\Http\Controllers;

      use App\Http\Controllers\Controller;
      use App\Models\User;

      class UserController extends Controller
      {
          /**
           * Show the profile for the given user.
           *
           * @param  int  $id
           * @return View
           */
          public function show($id)
          {
              return view('user.profile', ['user' => User::findOrFail($id)]);
          }
      }
* Tạo controller mới bằng CLI: **php artisan make:controller** ***`TÊN_CONTROLLER`***

# MODEL
* Cấu trúc một Model

      <?php

      namespace App\Models;

      use Illuminate\Database\Eloquent\Model;

      class Flight extends Model
      {
          //
      }
* Tạo Model mới bằng CLI: **php artisan make:model** ***`TÊN_MODEL`***
## Mối quan hệ
* 1 - 1:

      <?php

      namespace App\Models;

      use Illuminate\Database\Eloquent\Model;

      class User extends Model
      {
          /**
           * Get the phone record associated with the user.
           */
          public function phone()
          {
              //return $this->hasOne('App\Models\Phone', 'foreign_key', 'local_key');
              return $this->belongsTo('App\Models\TheLoai', ' foreign_key ', ' local_key ');
          }
      }

* 1 - nhiều:

      <?php

      namespace App\Models;

      use Illuminate\Database\Eloquent\Model;

      class Post extends Model
      {
          /**
           * Get the comments for the blog post.
           */
          public function comments()
          {
              return $this->hasMany('App\Models\Comment', 'foreign_key', 'local_key');
          }
      }


* Link giữa các bảng từ ( Thể Loại - > Loại Tin -> Tin Tức  )

      class Comment extends Model
      {
          /**
           * Get the post that owns the comment.
           */
          public function tintuc()
          {
              return $this->hasManyThrough('App\Models\TinTuc, 'Model Trung Gian ' ,'foreign_key_TrungGian', 'primary_key_LoaiTin' , 'local_key');
          }
      }

## Câu truy vấn Query

* GetAll :

      $user = App\Models\User::all();
* Get1 : 

      $user = App\Models\User::find(1);
* Query có điều kiện:

      $user->posts()
              ->where('active', 1)
              ->orWhere('votes', '>=', 100)
              ->get();
**...**

