---
title: "SqlMetal.exe (средство создания кода)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
caps.latest.revision: "43"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa4cf7baa3ca3ba19a733438920357034e8de193
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="501d0-102">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="501d0-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="501d0-103">Программа командной строки SqlMetal создает код и сопоставление для компонента [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="501d0-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="501d0-104">С помощью описанных ниже параметров можно настраивать SqlMetal на выполнение различных действий, включая следующие.</span><span class="sxs-lookup"><span data-stu-id="501d0-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="501d0-105">Создание исходного кода и атрибутов сопоставления или файла сопоставления на основе базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="501d0-106">Создание DBLM-файла для настройки на основе базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="501d0-107">Создание кода и атрибутов сопоставления или файла сопоставления на основе DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="501d0-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="501d0-108">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="501d0-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="501d0-109">По умолчанию файл располагается в папке `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="501d0-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="501d0-110">Если Visual Studio не установлена, файл SQLMetal можно получить, скачав [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="501d0-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501d0-111">Разработчики, работающие в Visual Studio также могут использовать [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] для создания классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="501d0-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="501d0-112">Командная строка удобна при работе с большими базами данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="501d0-113">Поскольку SqlMetal представляет собой программу командной строки, ее можно использовать в процессе построения.</span><span class="sxs-lookup"><span data-stu-id="501d0-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="501d0-114">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="501d0-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="501d0-115">Подробнее см. в разделе [Командная строка](../../../docs/framework/tools/developer-command-prompt-for-vs.md). В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="501d0-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="501d0-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="501d0-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="501d0-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="501d0-117">Options</span></span>  
 <span data-ttu-id="501d0-118">Чтобы просмотреть текущий список параметров, в командной строке введите `sqlmetal /?` в каталоге установки.</span><span class="sxs-lookup"><span data-stu-id="501d0-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="501d0-119">**Параметры подключения**</span><span class="sxs-lookup"><span data-stu-id="501d0-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="501d0-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="501d0-120">Option</span></span>|<span data-ttu-id="501d0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="501d0-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501d0-122">**/server:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="501d0-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="501d0-123">Задает имя сервера базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="501d0-124">**/database:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="501d0-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="501d0-125">Задает каталог базы данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="501d0-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="501d0-126">**/user:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="501d0-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="501d0-127">Задает идентификатор пользователя для входа. По умолчанию используется аутентификация Windows.</span><span class="sxs-lookup"><span data-stu-id="501d0-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="501d0-128">**/password:** *\<пароль>*</span><span class="sxs-lookup"><span data-stu-id="501d0-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="501d0-129">Задает пароль для входа.</span><span class="sxs-lookup"><span data-stu-id="501d0-129">Specifies logon password.</span></span> <span data-ttu-id="501d0-130">По умолчанию используется аутентификация Windows.</span><span class="sxs-lookup"><span data-stu-id="501d0-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="501d0-131">**/conn:** *\<строка подключения>*</span><span class="sxs-lookup"><span data-stu-id="501d0-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="501d0-132">Задает строку подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-132">Specifies database connection string.</span></span> <span data-ttu-id="501d0-133">Нельзя использовать с параметрами **/server**, **/database**, **/user**или **/password** .</span><span class="sxs-lookup"><span data-stu-id="501d0-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="501d0-134">В строке подключения не следует указывать имя файла.</span><span class="sxs-lookup"><span data-stu-id="501d0-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="501d0-135">Вместо этого добавьте имя файла в командную строку в качестве входного файла.</span><span class="sxs-lookup"><span data-stu-id="501d0-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="501d0-136">Например, в следующей строке указывается входной файл "c:\northwnd.mdf": **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="501d0-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="501d0-137">**/timeout:** *\<сек>*</span><span class="sxs-lookup"><span data-stu-id="501d0-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="501d0-138">Задает время ожидания для доступа SqlMetal к базе данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="501d0-139">Значение по умолчанию: 0 (то есть время не ограничено).</span><span class="sxs-lookup"><span data-stu-id="501d0-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="501d0-140">**Параметры извлечения**</span><span class="sxs-lookup"><span data-stu-id="501d0-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="501d0-141">Параметр</span><span class="sxs-lookup"><span data-stu-id="501d0-141">Option</span></span>|<span data-ttu-id="501d0-142">Описание</span><span class="sxs-lookup"><span data-stu-id="501d0-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501d0-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="501d0-143">**/views**</span></span>|<span data-ttu-id="501d0-144">Извлекает представления базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-144">Extracts database views.</span></span>|  
|<span data-ttu-id="501d0-145">**/functions**</span><span class="sxs-lookup"><span data-stu-id="501d0-145">**/functions**</span></span>|<span data-ttu-id="501d0-146">Извлекает функции базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="501d0-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="501d0-147">**/sprocs**</span></span>|<span data-ttu-id="501d0-148">Извлекает хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="501d0-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="501d0-149">**Параметры вывода**</span><span class="sxs-lookup"><span data-stu-id="501d0-149">**Output options**</span></span>  
  
|<span data-ttu-id="501d0-150">Параметр</span><span class="sxs-lookup"><span data-stu-id="501d0-150">Option</span></span>|<span data-ttu-id="501d0-151">Описание</span><span class="sxs-lookup"><span data-stu-id="501d0-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501d0-152">**/dbml** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="501d0-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="501d0-153">Направляет вывод в DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="501d0-153">Sends output as .dbml.</span></span> <span data-ttu-id="501d0-154">Не может использоваться с параметром **/map** .</span><span class="sxs-lookup"><span data-stu-id="501d0-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="501d0-155">**/code** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="501d0-155">**/code** *[:file]*</span></span>|<span data-ttu-id="501d0-156">Направляет вывод в файл исходного кода.</span><span class="sxs-lookup"><span data-stu-id="501d0-156">Sends output as source code.</span></span> <span data-ttu-id="501d0-157">Не может использоваться с параметром **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="501d0-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="501d0-158">**/map** *[:файл]*</span><span class="sxs-lookup"><span data-stu-id="501d0-158">**/map** *[:file]*</span></span>|<span data-ttu-id="501d0-159">Создает XML-файл сопоставления вместо атрибутов.</span><span class="sxs-lookup"><span data-stu-id="501d0-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="501d0-160">Не может использоваться с параметром **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="501d0-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="501d0-161">**Прочее**</span><span class="sxs-lookup"><span data-stu-id="501d0-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="501d0-162">Параметр</span><span class="sxs-lookup"><span data-stu-id="501d0-162">Option</span></span>|<span data-ttu-id="501d0-163">Описание</span><span class="sxs-lookup"><span data-stu-id="501d0-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501d0-164">**/language:** *\<язык>*</span><span class="sxs-lookup"><span data-stu-id="501d0-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="501d0-165">Задает язык исходного кода.</span><span class="sxs-lookup"><span data-stu-id="501d0-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="501d0-166">Допустимый *\<язык>*: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="501d0-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="501d0-167">Значение по умолчанию: определяется по расширению имени файла кода.</span><span class="sxs-lookup"><span data-stu-id="501d0-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="501d0-168">**/namespace:** *\<имя>*</span><span class="sxs-lookup"><span data-stu-id="501d0-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="501d0-169">Задает пространство имен сгенерированного кода.</span><span class="sxs-lookup"><span data-stu-id="501d0-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="501d0-170">Значение по умолчанию: пространство имен не определяется.</span><span class="sxs-lookup"><span data-stu-id="501d0-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="501d0-171">**/context:** *\<тип>*</span><span class="sxs-lookup"><span data-stu-id="501d0-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="501d0-172">Задает имя класса контекста данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-172">Specifies name of data context class.</span></span> <span data-ttu-id="501d0-173">Значение по умолчанию: определяется по имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="501d0-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="501d0-174">**/entitybase:** *\<тип>*</span><span class="sxs-lookup"><span data-stu-id="501d0-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="501d0-175">Задает базовый класс для классов сущностей в сгенерированном коде.</span><span class="sxs-lookup"><span data-stu-id="501d0-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="501d0-176">Значение по умолчанию: базовый класс для сущностей не определяется.</span><span class="sxs-lookup"><span data-stu-id="501d0-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="501d0-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="501d0-177">**/pluralize**</span></span>|<span data-ttu-id="501d0-178">Автоматически преобразует имена классов и членов в форму множественного или единственного числа.</span><span class="sxs-lookup"><span data-stu-id="501d0-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="501d0-179">Этот вариант доступен только в английской версии (США).</span><span class="sxs-lookup"><span data-stu-id="501d0-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="501d0-180">**/serialization:** *\<параметр>*</span><span class="sxs-lookup"><span data-stu-id="501d0-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="501d0-181">Создает сериализуемые классы.</span><span class="sxs-lookup"><span data-stu-id="501d0-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="501d0-182">Допустимые значения *\<параметра>*: нет, однонаправленный.</span><span class="sxs-lookup"><span data-stu-id="501d0-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="501d0-183">Значение по умолчанию: нет.</span><span class="sxs-lookup"><span data-stu-id="501d0-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="501d0-184">Дополнительные сведения см. в разделе [Сериализация](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="501d0-184">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="501d0-185">**Входной файл**</span><span class="sxs-lookup"><span data-stu-id="501d0-185">**Input File**</span></span>  
  
|<span data-ttu-id="501d0-186">Параметр</span><span class="sxs-lookup"><span data-stu-id="501d0-186">Option</span></span>|<span data-ttu-id="501d0-187">Описание</span><span class="sxs-lookup"><span data-stu-id="501d0-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501d0-188">**\<входной файл>**</span><span class="sxs-lookup"><span data-stu-id="501d0-188">**\<input file>**</span></span>|<span data-ttu-id="501d0-189">Задает MDF-файл SQL Server, экспресс-выпуск, SDF-файл [!INCLUDE[ssEW](../../../includes/ssew-md.md)] или промежуточный DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="501d0-189">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="501d0-190">Примечания</span><span class="sxs-lookup"><span data-stu-id="501d0-190">Remarks</span></span>  
 <span data-ttu-id="501d0-191">Функции SqlMetal фактически выполняются в два этапа.</span><span class="sxs-lookup"><span data-stu-id="501d0-191">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="501d0-192">Метаданные базы данных извлекаются в DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="501d0-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="501d0-193">Создается выходной файл кода.</span><span class="sxs-lookup"><span data-stu-id="501d0-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="501d0-194">Используя соответствующие параметры командной строки, можно получать исходный код [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] или C# либо XML-файл сопоставления.</span><span class="sxs-lookup"><span data-stu-id="501d0-194">By using the appropriate command-line options, you can produce [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="501d0-195">Чтобы извлечь метаданные из MDF-файла, необходимо указать его имя после всех остальных параметров.</span><span class="sxs-lookup"><span data-stu-id="501d0-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="501d0-196">Если не **/server** указан, предполагается **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="501d0-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 [!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)]<span data-ttu-id="501d0-197"> выдает исключение в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="501d0-197"> throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="501d0-198">SqlMetal пытается извлечь хранимую процедуру, вызывающую саму себя.</span><span class="sxs-lookup"><span data-stu-id="501d0-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="501d0-199">Уровень вложенности хранимой процедуры, функции или представления превышает 32 уровня.</span><span class="sxs-lookup"><span data-stu-id="501d0-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="501d0-200">SqlMetal перехватывает это исключение и сообщает о нем в виде предупреждения.</span><span class="sxs-lookup"><span data-stu-id="501d0-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="501d0-201">Чтобы указать имя входного файла, добавьте имя в командную строку в качестве входного файла.</span><span class="sxs-lookup"><span data-stu-id="501d0-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="501d0-202">Включение имени файла в строку подключения (параметром **/conn** ) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="501d0-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="501d0-203">Примеры</span><span class="sxs-lookup"><span data-stu-id="501d0-203">Examples</span></span>  
 <span data-ttu-id="501d0-204">Создание DBML-файла, содержащего извлеченные метаданные SQL.</span><span class="sxs-lookup"><span data-stu-id="501d0-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="501d0-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="501d0-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="501d0-206">Создание DBML-файла, содержащего извлеченные метаданные SQL из MDF-файла, с помощью SQL Server, экспресс-выпуск.</span><span class="sxs-lookup"><span data-stu-id="501d0-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="501d0-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="501d0-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="501d0-208">Создание DBML-файла, содержащего извлеченные метаданные SQL из SQL Server, экспресс-выпуск.</span><span class="sxs-lookup"><span data-stu-id="501d0-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="501d0-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="501d0-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="501d0-210">Создание исходного кода из DBML-файла метаданных.</span><span class="sxs-lookup"><span data-stu-id="501d0-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="501d0-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="501d0-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="501d0-212">Создание исходного кода непосредственно из метаданных SQL.</span><span class="sxs-lookup"><span data-stu-id="501d0-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="501d0-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="501d0-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501d0-214">При использовании параметра **/pluralize** вместе с учебной базой данных Northwind необходимо иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="501d0-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="501d0-215">Когда SqlMetal создает имена типов строк для таблиц, имена таблиц представляются в единственном числе.</span><span class="sxs-lookup"><span data-stu-id="501d0-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="501d0-216">При создании свойств <xref:System.Data.Linq.DataContext> для таблиц имена таблиц представляются во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="501d0-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="501d0-217">Однако таблицы в учебной базе данных Northwind уже имеют имена в форме множественного числа.</span><span class="sxs-lookup"><span data-stu-id="501d0-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="501d0-218">Поэтому данная часть процедуры не будет иметь видимого эффекта.</span><span class="sxs-lookup"><span data-stu-id="501d0-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="501d0-219">Если таблицам базы данных принято присваивать имена в единственном числе, то коллекциям .NET принято присваивать имена во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="501d0-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501d0-220">См. также</span><span class="sxs-lookup"><span data-stu-id="501d0-220">See Also</span></span>  
 [<span data-ttu-id="501d0-221">Как: Создание модели объектов в Visual Basic или C#</span><span class="sxs-lookup"><span data-stu-id="501d0-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 [<span data-ttu-id="501d0-222">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="501d0-222">Code Generation in LINQ to SQL</span></span>](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="501d0-223">Внешнее сопоставление</span><span class="sxs-lookup"><span data-stu-id="501d0-223">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
