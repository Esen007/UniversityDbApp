# UniversityDbApp — 3-апта зертханалық жұмысы

## Жоба мақсаты
EF Core арқылы MS SQL Server дерекқорымен байланыс орнату және Code-First миграциясын орындау.

## Модельдер
- `Department` — кафедра.
- `Teacher` — оқытушы.
- Байланыс: бір Department-та бірнеше Teacher болады (One-to-Many).
- `Teacher.DepartmentId` — сыртқы кілт (Foreign Key).

## Қажетті орта
- .NET 8 SDK
- SQL Server LocalDB немесе SQL Server
- Visual Studio Code

## Іске қосу және миграция
Терминалда жоба бумасында орындаңыз:

```powershell
dotnet restore
dotnet build
dotnet tool install --global dotnet-ef --version 8.0.11
dotnet ef migrations add InitialDb
dotnet ef database update
dotnet run
```

Егер `dotnet-ef` бұрын орнатылған болса, install командасының орнына:
`dotnet tool update --global dotnet-ef --version 8.0.11`

## SQL Server қосылымы
`appsettings.json` ішінде LocalDB қосылымы орнатылған:
`(localdb)\MSSQLLocalDB`, дерекқор атауы `UniversityDb`.

Егер компьютерде LocalDB жоқ болса, SQL Server орнатылған сервер атауына сәйкес
`DefaultConnection` жолын өзгертіңіз.

## Тапсыру
1. GitHub репозиторийіне жоба файлдарын жүктеңіз.
2. SSMS-та `UniversityDb > Tables` бөлімін ашып, `dbo.Departments` және
   `dbo.Teachers` кестелері көрінетін скриншот жасаңыз.
3. `dbo.Teachers` кестесіндегі `DepartmentId` сыртқы кілтін көрсетіңіз.
