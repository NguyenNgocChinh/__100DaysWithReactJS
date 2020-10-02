# LARAVEL

## MVC
	M: Model -> Đảm nhiệm nhiệm vụ làm việc với database.
	V: View -> Đảm nhiệm nhiệm vụ hiển thị cho người dùng cuối.
	C: Controller -> Đảm nhiệm nhiệm vụ xử lí các request, response trả view cho người dùng là gọi Model để xử lý dữ liệu.
## Cấu trúc thư mục
	Controller : app > Http > Controller
	View : resources > views 
	Model : app > Model
	Route : routes > web.php

## Blade
	Hiển thị biến == echo trong PHP
		Hello, {{  $name }}	- Với biến không có chứa các thẻ HTML
		Hello, {!! $name !!}	- Với biến có chứa các thẻ HTML
	 IF clause
		@if(4%2 ==0)
        			<p>DUNG</p>
        		@endif
	 For loop
		@for($i = 0; $i < 10; $i++)
        			@if($i%2 ==0)
        				<p>Cau : {{ $i }}</p>
        			@endif
    		@endfor
	 Foreach
		@foreach($arr as $phantu)
        			@if($loop->odd)
        				{{ $phantu }}
        			@endif
    		@endforeach

	 Kế Thừa từ 1 blade template khác
		@extends('master')

	 Quy định sự thay đổi trong layout master
		@yield('content')
	
	 Khai báo thay đổi của layout con được kế thừa từ layout master
		@section('content')
