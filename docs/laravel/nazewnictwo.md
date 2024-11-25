---
title: "Laravel - Nazewnictwo"
---


## Kontrolery

- nazwa klasy `PascalCase`
- nazwa klasy powinna być w liczbie pojedynczej (zwykle odnosząca się do konkretnego modelu)
- nazwa klasy powinna kończyć się na `Controller`
- nazwy zmiennych piszemy `camelCase`

**✅ Poprawne przykłady**

- `PostController`
- `BookController`
- `$users = User::paginate(50)`
- `$user = User::find(1)`

**❌ Niepoprawne nazwy**

- `BooksController` - liczba mnoga w nazwie
- `Books`
  - brakujący sufiks `Controller`
  - liczba mnoga w nazwie
- `$user = User::paginate(50)` - nazwa zmiennej powinna wskazywać na liczbę mnogą
- `$users = User::find(1)` - nazwa zmiennej powinna wskazywać na liczbę pojedyńczą

#### Routing i nazwy metod

- uri `kebab-case`
- nazwy metod w kontrolerze `camelCase`
- nazwy zwracanych widoków blade powinny być pisane `kebab-case` lub `snake_case`
- nazwy zwracanych widoków vue `PascalCase`
- nazwa trasy`camelCase`
- dla standardowych operacji CRUD nazwa routa powinna wskazywać na model w liczbie mnogiej i nazwę operacji modelu połaczonych kropką
- argument w trasie najczęściej powinien być zgodny z nazwą modelu, którego dane chcemy pobrać

**✅ Poprawne nazwy**

- `Route::delete('user-invitations/{userInvitation}', [UserInvitationController::class, 'destroy'])->name('userInvitations.destroy')` - uri
- `return view('about_us.blade.php')` lub `return view('about-us.blade.php')` - blade
- `return Inertia::render('AboutUs.vue')` - vue

**❌ Niepoprawne nazwy**

- `Route::delete('userInvitations/{invitation}', [UserInvitationController::class, 'delete'])->name('userInvitation.destroy')`
  - uri niezgodne z `kebab-case`
  - nazwa argumentu mogłaby być `userInvitation` zamiast `invitation`
  - nazwa metody `delete` zamiast `destroy`
  - w nazwie route użyto `userInvitation` w liczbie pojedynczej zamiast liczby mnogiej
- `return view('aboutUs.blade.php')` - nazwa widoku blade niezgodna z `kebab-case` i `snake_case`
- `return Inertia::render('about-us.vue')` - nazwa widoku vue niezgodna z `PascalCase`

**Dla standardowych operacji CRUD routing powinien wyglądać w ten sposób:**

<table>
<tr>
<th>Verb</th>
<th>URI</th>
<th>Action (controller method)</th>
<th>Route name</th>
</tr>
<tbody>
<tr>
<td>GET</td>
<td>/photos</td>
<td>index</td>
<td>photos.index</td>
</tr>
<tr>
<td>GET</td>
<td>/photos/create</td>
<td>create</td>
<td>photos.create</td>
</tr>
<tr>
<td>POST</td>
<td>/photos</td>
<td>store</td>
<td>photos.store</td>
</tr>
<tr>
<td>GET</td>
<td>/photos/{photo}</td>
<td>show</td>
<td>photos.show</td>
</tr>
<tr>
<td>GET</td>
<td>/photos/{photo}/edit</td>
<td>edit</td>
<td>photos.edit</td>
</tr>
<tr>
<td>PUT/PATCH</td>
<td>/photos/{photo}</td>
<td>update</td>
<td>photos.update</td>
</tr>
<tr>
<td>DELETE</td>
<td>/photos/{photo}</td>
<td>destroy</td>
<td>photos.destroy</td>
</tr>
</tbody>
</table>

## Tabele

- nazwa tabeli `snake_case` z \_
- nazwa tabeli powinna być w liczbie mnogiej
  - wyjątek stanowi tabela `pivot`, której nazwa powinna zawierać nazwy modeli w liczbie pojedynczej i kolejności alfabetycznej

**✅ Poprawne nazwy**

- `posts`
- `books`
- `book_user` (pivot)

**❌ Niepoprawne nazwy**

- `all_posts` - niepotrzebny prefiks `all_`
- `Posts` - nie przestrzega `snake_case`
- `book` - liczba pojedyncza zamiast mnogiej
- `user_book` (pivot) - nazwy modeli są niealfabetycznie
- `books_users` (pivot) - liczba mnoga zamiast pojedynczej w nazwach modeli

#### Kolumny w tabeli

- nazwa kolumny w `snake_case`
- nazwa kolumny nie powinna zawierać odniesienia do samej tabeli (poza ewentualnym kluczem obcym do tej samej tabeli)
- nazwa kolumny klucza obcego powinna składać się z modelu w liczbie pojedynczej w `snake_case` z dodanym sufiksem `_id`

**✅ Poprawne nazwy**

- `release_date`
- `title`,
- `user_id`

**❌ Niepoprawne nazwy**

- `book_release_date` - zbędne odniesienie do tabeli `book`
- `releaseDate` - nie przestrzega `snake_case`
- `users_id` - liczba mnoga zamiast pojedynczej

## Modele

- nazwa modelu `PascalCase`
- nazwa modelu powinna być w liczbie pojedynczej
- nazwa modelu nie powinna zawierać dodatkowych prefiksow ani sufiksów, model powinien rozpoznać nazwę odpowiadającej tabeli na podstawie swojej nazwy

**✅ Poprawne nazwy**

- `Book`
- `Post`

**❌ Niepoprawne nazwy**

- `author_book` - nie przestrzega `snake_case`
- `BookModel` - zbędny sufiks, uniemożliwia automatyczne rozpoznanie tabeli
- `Books` - liczba mnoga zamiast pojedynczej

#### Metody w modelu

- nazwy metod `camelCase`
- dla relacji `hasOne`, `belongsTo`, `hasOneThrough` nazwa powinna być w liczbie pojedynczej i odwoływać się do powiązanego modelu
- dla relacji `hasMany`, `belongsToMany`, `hasManyThrough` nazwa powinna być w liczbie mnogiej i odwoływać się do powiązanego modelu

**✅ Poprawne nazwy**

- `public function mainCategory()`
- `public function authors()`
- `public function tags()`

**❌ Niepoprawne nazwy**

- `public function Authors()` - nie przestrzega `camelCase`
- `public function getAuthors()` - zbędny prefiks `get`

<!-- komenda do generowania modelu, kontrolera i migracji
php artisan make:model -m ForumPost -mvc -->

## Generowanie klas

Laravel zapewnia komendę która można od razu wygenerować model, migration, controller, policy, form requests, factory i seeder:
[https://laravel.com/docs/11.x/eloquent#generating-model-classes](https://laravel.com/docs/11.x/eloquent#generating-model-classes)
