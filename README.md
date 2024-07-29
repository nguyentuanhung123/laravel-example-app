<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Học Laravel

## Day 1: Hello, Laravel
- B1: Tải Laravel Herd
- B2: Mở terminal, chạy lệnh Laravel new example-app
- B3: Chọn No starter ket -> Pest -> no
- B4: Chọn SQLite
- B5: Mở trình duyệt và paste example-app.test

## Day 2: Your First Route and View
- Mở Project đã tạo trên phpstorm bang cách mở Terminal của project đó và chạy phpstorm .
- Câu lệnh mới sẽ học sau: php artisan serve
- Phân tích cách chạy và sửa trang homepage
- B1: Vào file web.php và bổ sung

```php
Route::get('/about', function () {
   return view('about');
});
```

- B2: Tạo file about.php và viết html bất kỳ bên trong
- B3: Vào trình duyêt chạy http://example-app.test/about

- Lưu ý nhỏ: Nếu ta có

```php
Route::get('/about', function () {
    return ['foo' => 'bar'];
});
```

- Thì khi vào trình duyêt chạy http://example-app.test/about. nó sẽ ra

```html
{
  "foo": "bar"
}
```

- Lý do là bởi Hàm ẩn danh trả về một mảng với một cặp khóa-giá trị. Ở đây, khóa là 'foo' và giá trị là 'bar'.
  Laravel tự động chuyển đổi mảng này thành định dạng JSON khi trả về HTTP response.

## Day 3: Create a Layout File Using Laravel Components

- Thay đổi file welcome.blade.php thành home.php:
- B1: chuột phải -> Reflactor -> Do Reflactor
- B2: Sửa lại đường dẫn mặc định ban đầu trong web.php thành

```jsx
Route::get('/', function () {
    return view('home');
});
```

- Thay đổi tất cả các file chỉ có .php thành .blade.php. Trong Laravel, các tệp view được khuyến khích sử dụng 
đuôi tệp .blade.php thay vì chỉ .php vì chúng sử dụng Blade, engine template của Laravel. 
Blade được biên dịch thành mã PHP thuần, nên hiệu suất khi sử dụng Blade và các tệp .blade.php là rất tốt. 
Laravel sẽ biên dịch các tệp Blade thành các tệp PHP thuần và lưu trữ chúng trong bộ nhớ cache, giúp tăng hiệu suất ứng dụng.


- Tạo 1 component dùng chung như Navbar để chuyển hướng trang 
- B1: Tạo file layout.blade.php trong folder Components (folder Components nằm trong folder views)
- B2: Copy thẻ html ban đầu trong home.blade.php và paste sang layout.blade.php
- B3: Xóa thẻ h1 ban đầu thay bằng thẻ nav và {{ slots }}

```bladehtml
<body>
     <nav>
         <a href="/">Home</a>
         <a href="/about">About</a>
         <a href="/contact">Contact</a>
     </nav>

     {{ $slot }}
</body>
```

- B4: Vào các file .blade.php trong view và xóa hết các thẻ html và chỉ giữ lại các thẻ cần thiết và bọc nó trong <x-layout>

```bladehtml
<x-layout>
    <h1>Hello from the contact page</h1>
</x-layout>
```

- Lưu ý nhỏ: Do ta đặt tên các file có đuôi blade.php nên ta chỉ cần viết là {{ slots }}, chứ nếu là file .php bình thường ta phải viết 
là : 

```php
<?php echo slot ?>
```

# Logic được rút ra trong bài này
- Khi ta chạy vào đường dẫn "/", thì nó sẽ chạy file home.blade.php
- Các thẻ trong home.blade.php được bọc trong <x-layout>...</x-layout> nên file layout.blade.php sẽ được chạy trước
- Khi đến đoạn {{ slot }} trong file layout.blade.php thì những thẻ trong file home.blade.php mới được chạy

# Cách nhớ dễ trong bài này

- Trong file .blade.php dùng chung: Giống nhau thì giữ nguyên khác biệt chỗ nào thì thay bằng slot
- Trong file .blade.php dùng riêng: Bọc nó trong <x-...></x-...> và viết ra chỗ khác biệt
- Trong file dùng chung như layout.blade.php bắt buộc phải có {{ slot }} để hiện thứ khác biệt
- File chung có slot, file riêng thì không

# Để có thể lấy các attribite trong thẻ <x-... style="" href></x-...> thì ta sử dụng attribute

- Ví dụ: 

```bladehtml
<x-nav-link href="/">Home</x-nav-link>
```

```bladehtml
<a {{ $attribute }}>{{ $slot }}</a>
```

## Day 4: Make a Pretty Layout Using TailwindCSS

- B1: Copy và paste 1 ui của tailwinđ như navbar vào layout.blade.php
- B2: Add script để kết nối với tailwind css

```bladehtml
<script src="https://cdn.tailwindcss.com"></script>
```

# Ta muốn khi chuyển đổi trang thì heading ở file chung như layout.blade.php cũng sẽ được đổi

-  Ở file layout.blade.php ta có:

```bladehtml
<header class="bg-white shadow">
    <div class="mx-auto max-w-7xl px-4 py-6 sm:px-6 lg:px-8">
        <h1 class="text-3xl font-bold tracking-tight text-gray-900">{{ $heading }}</h1>
    </div>
</header>
```

- Th ở file riêng để có thể sử dụng heading ta phải viết là

```bladehtml
<x-layout>
    <x-slot:heading>
        About Page
    </x-slot:heading>
    <h1>Hello from the about page</h1>
</x-layout>
```



