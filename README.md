# Экспортын дашбоард

Амьтны гаралтай бүтээгдэхүүний экспортын интерактив дашбоард.

## Төслийн бүтэц

```text
export-dashboard-vercel/
├── index.html
├── README.md
├── .gitignore
└── vercel.json
```

`index.html` файл дотор Plotly, dashboard-ийн JavaScript логик болон `RAW_DATA` өгөгдөл бүгд багтсан. Тусдаа backend, database, Node.js package эсвэл build process шаардлагагүй.

## Local дээр ажиллуулах

### Хамгийн энгийн арга
`index.html` файлыг browser-оор шууд нээж болно.

### Local server ашиглах
Python суусан бол төслийн хавтсанд Terminal нээгээд:

```bash
python -m http.server 8000
```

Дараа нь browser дээр:

```text
http://localhost:8000
```

## GitHub руу оруулах

GitHub дээр шинэ repository үүсгээд энэ хавтас дотор Terminal нээнэ:

```bash
git init
git add .
git commit -m "Initial export dashboard"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

`YOUR_USERNAME` болон `YOUR_REPOSITORY` хэсгийг өөрийн GitHub мэдээллээр солино.

## Vercel дээр deploy хийх

1. Vercel → **Add New → Project**.
2. GitHub repository-гаа сонгоод **Import**.
3. **Framework Preset:** `Other`.
4. **Root Directory:** `./` хэвээр үлдээнэ.
5. Build command шаардлагагүй.
6. **Deploy** дарна.

Deploy дууссаны дараа Vercel `https://your-project.vercel.app` хэлбэрийн public URL өгнө.

## Шинэчлэлт хийх

`index.html`-ээ өөрчилсний дараа:

```bash
git add .
git commit -m "Update dashboard"
git push
```

GitHub-тэй холбогдсон Vercel project автоматаар дахин deploy хийнэ.

## Тэмдэглэл

- Google Fonts интернетээр ачаалагдана.
- Dashboard-ийн үндсэн өгөгдөл `index.html` дотор суусан тул тусдаа Excel/CSV файл upload хийх шаардлагагүй.
- Repository-ийн үндсэн хуудсыг Vercel зөв танихын тулд гол файл `index.html` нэртэй байна.
