---
title: "SqlMetal.exe (средство создания кода)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
caps.latest.revision: 43
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6d0ac9c682c60db8eb9e5188a71916dc5d97de60
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="cb051-102">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="cb051-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="cb051-103">Программа командной строки SqlMetal создает код и сопоставление для компонента [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb051-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="cb051-104">С помощью описанных ниже параметров можно настраивать SqlMetal на выполнение различных действий, включая следующие.</span><span class="sxs-lookup"><span data-stu-id="cb051-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="cb051-105">Создание исходного кода и атрибутов сопоставления или файла сопоставления на основе базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="cb051-106">Создание DBLM-файла для настройки на основе базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="cb051-107">Создание кода и атрибутов сопоставления или файла сопоставления на основе DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="cb051-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="cb051-108">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb051-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="cb051-109">По умолчанию файл располагается в папке `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="cb051-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="cb051-110">Если Visual Studio не установлена, файл SQLMetal можно получить, скачав [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="cb051-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb051-111">Разработчики, работающие в Visual Studio также могут использовать [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] для создания классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="cb051-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="cb051-112">Командная строка удобна при работе с большими базами данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="cb051-113">Поскольку SqlMetal представляет собой программу командной строки, ее можно использовать в процессе построения.</span><span class="sxs-lookup"><span data-stu-id="cb051-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="cb051-114">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="cb051-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="cb051-115">Подробнее см. в разделе [Командная строка](../../../docs/framework/tools/developer-command-prompt-for-vs.md). В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="cb051-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb051-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb051-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="cb051-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb051-117">Options</span></span>  
 <span data-ttu-id="cb051-118">Чтобы просмотреть текущий список параметров, в командной строке введите `sqlmetal /?` в каталоге установки.</span><span class="sxs-lookup"><span data-stu-id="cb051-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="cb051-119">**Параметры подключения**</span><span class="sxs-lookup"><span data-stu-id="cb051-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="cb051-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="cb051-120">Option</span></span>|<span data-ttu-id="cb051-121">Описание</span><span class="sxs-lookup"><span data-stu-id="cb051-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cb051-122">**/server:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="cb051-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="cb051-123">Задает имя сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="cb051-124">**/database:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="cb051-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="cb051-125">Задает каталог базы данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="cb051-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="cb051-126">**/user:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="cb051-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="cb051-127">Задает идентификатор пользователя для входа.</span><span class="sxs-lookup"><span data-stu-id="cb051-127">Specifies logon user id.</span></span> <span data-ttu-id="cb051-128">По умолчанию используется аутентификация Windows.</span><span class="sxs-lookup"><span data-stu-id="cb051-128">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="cb051-129">**/password:** *\<пароль>*</span><span class="sxs-lookup"><span data-stu-id="cb051-129">**/password:** *\<password>*</span></span>|<span data-ttu-id="cb051-130">Задает пароль для входа.</span><span class="sxs-lookup"><span data-stu-id="cb051-130">Specifies logon password.</span></span> <span data-ttu-id="cb051-131">По умолчанию используется аутентификация Windows.</span><span class="sxs-lookup"><span data-stu-id="cb051-131">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="cb051-132">**/conn:** *\<строка подключения>*</span><span class="sxs-lookup"><span data-stu-id="cb051-132">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="cb051-133">Задает строку подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-133">Specifies database connection string.</span></span> <span data-ttu-id="cb051-134">Нельзя использовать с параметрами **/server**, **/database**, **/user**или **/password** .</span><span class="sxs-lookup"><span data-stu-id="cb051-134">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="cb051-135">В строке подключения не следует указывать имя файла.</span><span class="sxs-lookup"><span data-stu-id="cb051-135">Do not include the file name in the connection string.</span></span> <span data-ttu-id="cb051-136">Вместо этого добавьте имя файла в командную строку в качестве входного файла.</span><span class="sxs-lookup"><span data-stu-id="cb051-136">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="cb051-137">Например, в следующей строке указывается входной файл "c:\northwnd.mdf": **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="cb051-137">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="cb051-138">**/timeout:** *\<сек>*</span><span class="sxs-lookup"><span data-stu-id="cb051-138">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="cb051-139">Задает время ожидания для доступа SqlMetal к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-139">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="cb051-140">Значение по умолчанию: 0 (то есть время не ограничено).</span><span class="sxs-lookup"><span data-stu-id="cb051-140">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="cb051-141">**Параметры извлечения**</span><span class="sxs-lookup"><span data-stu-id="cb051-141">**Extraction options**</span></span>  
  
|<span data-ttu-id="cb051-142">Параметр</span><span class="sxs-lookup"><span data-stu-id="cb051-142">Option</span></span>|<span data-ttu-id="cb051-143">Описание</span><span class="sxs-lookup"><span data-stu-id="cb051-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cb051-144">**/views**</span><span class="sxs-lookup"><span data-stu-id="cb051-144">**/views**</span></span>|<span data-ttu-id="cb051-145">Извлекает представления базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-145">Extracts database views.</span></span>|  
|<span data-ttu-id="cb051-146">**/functions**</span><span class="sxs-lookup"><span data-stu-id="cb051-146">**/functions**</span></span>|<span data-ttu-id="cb051-147">Извлекает функции базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-147">Extracts database functions.</span></span>|  
|<span data-ttu-id="cb051-148">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="cb051-148">**/sprocs**</span></span>|<span data-ttu-id="cb051-149">Извлекает хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb051-149">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="cb051-150">**Параметры вывода**</span><span class="sxs-lookup"><span data-stu-id="cb051-150">**Output options**</span></span>  
  
|<span data-ttu-id="cb051-151">Параметр</span><span class="sxs-lookup"><span data-stu-id="cb051-151">Option</span></span>|<span data-ttu-id="cb051-152">Описание</span><span class="sxs-lookup"><span data-stu-id="cb051-152">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cb051-153">**/dbml** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="cb051-153">**/dbml** *[:file]*</span></span>|<span data-ttu-id="cb051-154">Направляет вывод в DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="cb051-154">Sends output as .dbml.</span></span> <span data-ttu-id="cb051-155">Не может использоваться с параметром **/map** .</span><span class="sxs-lookup"><span data-stu-id="cb051-155">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="cb051-156">**/code** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="cb051-156">**/code** *[:file]*</span></span>|<span data-ttu-id="cb051-157">Направляет вывод в файл исходного кода.</span><span class="sxs-lookup"><span data-stu-id="cb051-157">Sends output as source code.</span></span> <span data-ttu-id="cb051-158">Не может использоваться с параметром **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="cb051-158">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="cb051-159">**/map** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="cb051-159">**/map** *[:file]*</span></span>|<span data-ttu-id="cb051-160">Создает XML-файл сопоставления вместо атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cb051-160">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="cb051-161">Не может использоваться с параметром **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="cb051-161">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="cb051-162">**Прочее**</span><span class="sxs-lookup"><span data-stu-id="cb051-162">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="cb051-163">Параметр</span><span class="sxs-lookup"><span data-stu-id="cb051-163">Option</span></span>|<span data-ttu-id="cb051-164">Описание</span><span class="sxs-lookup"><span data-stu-id="cb051-164">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cb051-165">**/language:** *\<язык>*</span><span class="sxs-lookup"><span data-stu-id="cb051-165">**/language:** *\<language>*</span></span>|<span data-ttu-id="cb051-166">Задает язык исходного кода.</span><span class="sxs-lookup"><span data-stu-id="cb051-166">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="cb051-167">Допустимый *\<язык>*: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="cb051-167">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="cb051-168">Значение по умолчанию: определяется по расширению имени файла кода.</span><span class="sxs-lookup"><span data-stu-id="cb051-168">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="cb051-169">**/namespace:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="cb051-169">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="cb051-170">Задает пространство имен сгенерированного кода.</span><span class="sxs-lookup"><span data-stu-id="cb051-170">Specifies namespace of the generated code.</span></span> <span data-ttu-id="cb051-171">Значение по умолчанию: пространство имен не определяется.</span><span class="sxs-lookup"><span data-stu-id="cb051-171">Default value: no namespace.</span></span>|  
|<span data-ttu-id="cb051-172">**/context:** *\<тип>*</span><span class="sxs-lookup"><span data-stu-id="cb051-172">**/context:** *\<type>*</span></span>|<span data-ttu-id="cb051-173">Задает имя класса контекста данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-173">Specifies name of data context class.</span></span> <span data-ttu-id="cb051-174">Значение по умолчанию: определяется по имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb051-174">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="cb051-175">**/entitybase:** *\<тип>*</span><span class="sxs-lookup"><span data-stu-id="cb051-175">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="cb051-176">Задает базовый класс для классов сущностей в сгенерированном коде.</span><span class="sxs-lookup"><span data-stu-id="cb051-176">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="cb051-177">Значение по умолчанию: базовый класс для сущностей не определяется.</span><span class="sxs-lookup"><span data-stu-id="cb051-177">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="cb051-178">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="cb051-178">**/pluralize**</span></span>|<span data-ttu-id="cb051-179">Автоматически преобразует имена классов и членов в форму множественного или единственного числа.</span><span class="sxs-lookup"><span data-stu-id="cb051-179">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="cb051-180">Этот вариант доступен только в английской версии (США).</span><span class="sxs-lookup"><span data-stu-id="cb051-180">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="cb051-181">**/serialization:** *\<параметр>*</span><span class="sxs-lookup"><span data-stu-id="cb051-181">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="cb051-182">Создает сериализуемые классы.</span><span class="sxs-lookup"><span data-stu-id="cb051-182">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="cb051-183">Допустимые значения *\<параметра>*: нет, однонаправленный.</span><span class="sxs-lookup"><span data-stu-id="cb051-183">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="cb051-184">Значение по умолчанию: нет.</span><span class="sxs-lookup"><span data-stu-id="cb051-184">Default value: None.</span></span><br /><br /> <span data-ttu-id="cb051-185">Дополнительные сведения см. в разделе [Сериализация](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="cb051-185">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="cb051-186">**Входной файл**</span><span class="sxs-lookup"><span data-stu-id="cb051-186">**Input File**</span></span>  
  
|<span data-ttu-id="cb051-187">Параметр</span><span class="sxs-lookup"><span data-stu-id="cb051-187">Option</span></span>|<span data-ttu-id="cb051-188">Описание</span><span class="sxs-lookup"><span data-stu-id="cb051-188">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cb051-189">**\<входной файл>**</span><span class="sxs-lookup"><span data-stu-id="cb051-189">**\<input file>**</span></span>|<span data-ttu-id="cb051-190">Задает MDF-файл SQL Server, экспресс-выпуск, SDF-файл [!INCLUDE[ssEW](../../../includes/ssew-md.md)] или промежуточный DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="cb051-190">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb051-191">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb051-191">Remarks</span></span>  
 <span data-ttu-id="cb051-192">Функции SqlMetal фактически выполняются в два этапа.</span><span class="sxs-lookup"><span data-stu-id="cb051-192">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="cb051-193">Метаданные базы данных извлекаются в DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="cb051-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="cb051-194">Создается выходной файл кода.</span><span class="sxs-lookup"><span data-stu-id="cb051-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="cb051-195">Используя соответствующие параметры командной строки, можно получать исходный код [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] или C# либо XML-файл сопоставления.</span><span class="sxs-lookup"><span data-stu-id="cb051-195">By using the appropriate command-line options, you can produce [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="cb051-196">Чтобы извлечь метаданные из MDF-файла, необходимо указать его имя после всех остальных параметров.</span><span class="sxs-lookup"><span data-stu-id="cb051-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="cb051-197">Если не **/server** указан, предполагается **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="cb051-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 [!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)]<span data-ttu-id="cb051-198"> выдает исключение в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="cb051-198"> throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="cb051-199">SqlMetal пытается извлечь хранимую процедуру, вызывающую саму себя.</span><span class="sxs-lookup"><span data-stu-id="cb051-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="cb051-200">Уровень вложенности хранимой процедуры, функции или представления превышает 32 уровня.</span><span class="sxs-lookup"><span data-stu-id="cb051-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="cb051-201">SqlMetal перехватывает это исключение и сообщает о нем в виде предупреждения.</span><span class="sxs-lookup"><span data-stu-id="cb051-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="cb051-202">Чтобы указать имя входного файла, добавьте имя в командную строку в качестве входного файла.</span><span class="sxs-lookup"><span data-stu-id="cb051-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="cb051-203">Включение имени файла в строку подключения (параметром **/conn** ) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cb051-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cb051-204">Примеры</span><span class="sxs-lookup"><span data-stu-id="cb051-204">Examples</span></span>  
 <span data-ttu-id="cb051-205">Создание DBML-файла, содержащего извлеченные метаданные SQL.</span><span class="sxs-lookup"><span data-stu-id="cb051-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="cb051-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="cb051-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="cb051-207">Создание DBML-файла, содержащего извлеченные метаданные SQL из MDF-файла, с помощью SQL Server, экспресс-выпуск.</span><span class="sxs-lookup"><span data-stu-id="cb051-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="cb051-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="cb051-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="cb051-209">Создание DBML-файла, содержащего извлеченные метаданные SQL из SQL Server, экспресс-выпуск.</span><span class="sxs-lookup"><span data-stu-id="cb051-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="cb051-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="cb051-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="cb051-211">Создание исходного кода из DBML-файла метаданных.</span><span class="sxs-lookup"><span data-stu-id="cb051-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="cb051-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="cb051-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="cb051-213">Создание исходного кода непосредственно из метаданных SQL.</span><span class="sxs-lookup"><span data-stu-id="cb051-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="cb051-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="cb051-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb051-215">При использовании параметра **/pluralize** вместе с учебной базой данных Northwind необходимо иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="cb051-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="cb051-216">Когда SqlMetal создает имена типов строк для таблиц, имена таблиц представляются в единственном числе.</span><span class="sxs-lookup"><span data-stu-id="cb051-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="cb051-217">При создании свойств <xref:System.Data.Linq.DataContext> для таблиц имена таблиц представляются во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="cb051-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="cb051-218">Однако таблицы в учебной базе данных Northwind уже имеют имена в форме множественного числа.</span><span class="sxs-lookup"><span data-stu-id="cb051-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="cb051-219">Поэтому данная часть процедуры не будет иметь видимого эффекта.</span><span class="sxs-lookup"><span data-stu-id="cb051-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="cb051-220">Если таблицам базы данных принято присваивать имена в единственном числе, то коллекциям .NET принято присваивать имена во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="cb051-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb051-221">См. также</span><span class="sxs-lookup"><span data-stu-id="cb051-221">See Also</span></span>  
 <span data-ttu-id="cb051-222">[Практическое руководство. Создание модели объектов в Visual Basic или C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md) </span><span class="sxs-lookup"><span data-stu-id="cb051-222">[How to: Generate the Object Model in Visual Basic or C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md) </span></span>  
 <span data-ttu-id="cb051-223">[Создание кода в LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md) </span><span class="sxs-lookup"><span data-stu-id="cb051-223">[Code Generation in LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md) </span></span>  
 [<span data-ttu-id="cb051-224">Внешнее сопоставление</span><span class="sxs-lookup"><span data-stu-id="cb051-224">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)

