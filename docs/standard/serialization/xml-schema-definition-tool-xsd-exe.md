---
title: XML Schema Definition Tool (Xsd.exe)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 08e612ccc55cf85929d0b16217259d73510bc15e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="3c09c-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="3c09c-102">XML Schema Definition Tool (Xsd.exe)</span></span>
<span data-ttu-id="3c09c-103">Инструмент определения схемы XML (Xsd.exe) создает схему XML или классы CLR из файлов XDR, XML и XSD либо из классов в сборке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c09c-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c09c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c09c-104">Syntax</span></span>  
  
```  
xsd file.xdr [/outputdir:directory][/parameters:file.xml]  
xsd file.xml [/outputdir:directory] [/parameters:file.xml]  
xsd file.xsd {/classes | /dataset} [/element:element]   
             [/enableLinqDataSet] [/language:language]   
                          [/namespace:namespace] [/outputdir:directory] [URI:uri]   
                          [/parameters:file.xml]  
xsd {file.dll | file.exe} [/outputdir:directory] [/type:typename [...]][/parameters:file.xml]  
```  
  
## <a name="argument"></a><span data-ttu-id="3c09c-105">Аргумент</span><span class="sxs-lookup"><span data-stu-id="3c09c-105">Argument</span></span>  
  
|<span data-ttu-id="3c09c-106">Аргумент</span><span class="sxs-lookup"><span data-stu-id="3c09c-106">Argument</span></span>|<span data-ttu-id="3c09c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="3c09c-108">*file.extension*</span><span class="sxs-lookup"><span data-stu-id="3c09c-108">*file.extension*</span></span>|<span data-ttu-id="3c09c-109">Задает входной файл, который необходимо преобразовать.</span><span class="sxs-lookup"><span data-stu-id="3c09c-109">Specifies the input file to convert.</span></span> <span data-ttu-id="3c09c-110">Следует указать одно из следующих расширений: XDR, XML, XSD, DLL или EXE.</span><span class="sxs-lookup"><span data-stu-id="3c09c-110">You must specify the extensionas one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="3c09c-111">Если указать файл схемы XDR (расширение XDR), Xsd.exe преобразует схему XDR в схему XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-111">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="3c09c-112">Имя выходного файла аналогично имени схемы XDR, но имеет расширение XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-112">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="3c09c-113">Если указать XML-файл (расширение XML), Xsd.exe определяет схему по данным в файле и создает схему XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-113">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="3c09c-114">Имя выходного файла аналогично имени XML-файла, но имеет расширение XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-114">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="3c09c-115">Если указать файл схемы XML (расширение XSD), Xsd.exe создает исходный код для объектов среды выполнения, соответствующих схеме XML.</span><span class="sxs-lookup"><span data-stu-id="3c09c-115">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="3c09c-116">Если указать файл сборки среды выполнения (расширение EXE или DLL), Xsd.exe создает схемы для одного или нескольких типов в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="3c09c-116">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="3c09c-117">Чтобы указать типы, для которых необходимо создать схемы, можно использовать параметр `/type`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-117">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="3c09c-118">Выходным схемам присваиваются имена schema0.xsd, schema1.xsd и т. д.</span><span class="sxs-lookup"><span data-stu-id="3c09c-118">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="3c09c-119">Xsd.exe создает несколько схем, только если указанные типы задают пространство имен с использованием настраиваемого атрибута `XMLRoot`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-119">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|  
  
## <a name="general-options"></a><span data-ttu-id="3c09c-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3c09c-120">General Options</span></span>  
  
|<span data-ttu-id="3c09c-121">Параметр</span><span class="sxs-lookup"><span data-stu-id="3c09c-121">Option</span></span>|<span data-ttu-id="3c09c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3c09c-123">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="3c09c-123">**/h**[**elp**]</span></span>|<span data-ttu-id="3c09c-124">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="3c09c-124">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="3c09c-125">**/ o**[**utputdir**] **: *** каталога*</span><span class="sxs-lookup"><span data-stu-id="3c09c-125">**/o**[**utputdir**]**:***directory*</span></span>|<span data-ttu-id="3c09c-126">Задает каталог выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="3c09c-126">Specifies the directory for output files.</span></span> <span data-ttu-id="3c09c-127">Этот аргумент отображается только один раз.</span><span class="sxs-lookup"><span data-stu-id="3c09c-127">This argument can appear only once.</span></span> <span data-ttu-id="3c09c-128">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-128">The default is the current directory.</span></span>|  
|<span data-ttu-id="3c09c-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="3c09c-129">**/?**</span></span>|<span data-ttu-id="3c09c-130">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="3c09c-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="3c09c-131">**/P[arameters]:** *file.xml*</span><span class="sxs-lookup"><span data-stu-id="3c09c-131">**/P[arameters]:** *file.xml*</span></span>|<span data-ttu-id="3c09c-132">Считывает параметры различных режимов операций из указанного XML-файла.</span><span class="sxs-lookup"><span data-stu-id="3c09c-132">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="3c09c-133">Краткая форма "/p:".</span><span class="sxs-lookup"><span data-stu-id="3c09c-133">The short form is '/p:'.</span></span> <span data-ttu-id="3c09c-134">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3c09c-134">For more information, see the following Remarks section.</span></span>|  
  
## <a name="xsd-file-options"></a><span data-ttu-id="3c09c-135">Параметры файла XSD</span><span class="sxs-lookup"><span data-stu-id="3c09c-135">XSD File Options</span></span>  
 <span data-ttu-id="3c09c-136">Для файлов XSD следует указать только один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3c09c-136">You must specify only one of the following options for .xsd files.</span></span>  
  
|<span data-ttu-id="3c09c-137">Параметр</span><span class="sxs-lookup"><span data-stu-id="3c09c-137">Option</span></span>|<span data-ttu-id="3c09c-138">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3c09c-139">**/c**[**lasses**]</span><span class="sxs-lookup"><span data-stu-id="3c09c-139">**/c**[**lasses**]</span></span>|<span data-ttu-id="3c09c-140">Создает классы, соответствующие указанной схеме.</span><span class="sxs-lookup"><span data-stu-id="3c09c-140">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="3c09c-141">Чтобы считать данные XML в объект, используйте метод `System.Xml.Serialization.XmlSerializer.Deserializer`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-141">To read XML data into the object, use the `System.Xml.Serialization.XmlSerializer.Deserializer` method.</span></span>|  
|<span data-ttu-id="3c09c-142">**/d**[**ataset**]</span><span class="sxs-lookup"><span data-stu-id="3c09c-142">**/d**[**ataset**]</span></span>|<span data-ttu-id="3c09c-143">Создает классы, которые являются производными класса <xref:System.Data.DataSet> и соответствуют указанной схеме.</span><span class="sxs-lookup"><span data-stu-id="3c09c-143">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="3c09c-144">Чтобы считать данные XML в производный класс, используйте метод `System.Data.DataSet.ReadXml`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-144">To read XML data into the derived class, use the `System.Data.DataSet.ReadXml` method.</span></span>|  
  
 <span data-ttu-id="3c09c-145">Для файлов XSD также можно указать любой из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3c09c-145">You can also specify any of the following options for .xsd files.</span></span>  
  
|<span data-ttu-id="3c09c-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="3c09c-146">Option</span></span>|<span data-ttu-id="3c09c-147">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-147">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3c09c-148">**/e**[**элементам**] **: *** элемент*</span><span class="sxs-lookup"><span data-stu-id="3c09c-148">**/e**[**lement**]**:***element*</span></span>|<span data-ttu-id="3c09c-149">Определяет элемент в схеме, для которого создается код.</span><span class="sxs-lookup"><span data-stu-id="3c09c-149">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="3c09c-150">По умолчанию все элементы имеют тип.</span><span class="sxs-lookup"><span data-stu-id="3c09c-150">By default all elements are typed.</span></span> <span data-ttu-id="3c09c-151">Этот аргумент можно задать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="3c09c-151">You can specify this argument more than once.</span></span>|  
|<span data-ttu-id="3c09c-152">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="3c09c-152">**/enableDataBinding**</span></span>|<span data-ttu-id="3c09c-153">Реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> для всех созданных типов для обеспечения привязки данных.</span><span class="sxs-lookup"><span data-stu-id="3c09c-153">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="3c09c-154">Краткая форма: `/edb`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-154">The short form is `/edb`.</span></span>|  
|<span data-ttu-id="3c09c-155">**/enableLinqDataSet**</span><span class="sxs-lookup"><span data-stu-id="3c09c-155">**/enableLinqDataSet**</span></span>|<span data-ttu-id="3c09c-156">(Краткая форма: `/eld`.) Указывает, что созданный набор данных можно запросить с помощью LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="3c09c-156">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="3c09c-157">Этот параметр используется только при указании параметра /dataset.</span><span class="sxs-lookup"><span data-stu-id="3c09c-157">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="3c09c-158">Дополнительные сведения см. в разделах [Общие сведения о LINQ to DataSet](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) и [Запрос к типизированным объектам DataSet](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="3c09c-158">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="3c09c-159">Общие сведения об использовании LINQ см. в разделе [LINQ](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="3c09c-159">For general information about using LINQ, see [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span>|  
|<span data-ttu-id="3c09c-160">**/f**[**ields**]</span><span class="sxs-lookup"><span data-stu-id="3c09c-160">**/f**[**ields**]</span></span>|<span data-ttu-id="3c09c-161">Создает поля вместо свойств.</span><span class="sxs-lookup"><span data-stu-id="3c09c-161">Generates fields instead of properties.</span></span> <span data-ttu-id="3c09c-162">По умолчанию создаются свойства.</span><span class="sxs-lookup"><span data-stu-id="3c09c-162">By default, properties are generated.</span></span>|  
|<span data-ttu-id="3c09c-163">**/l**[**anguage**] **: *** языка*</span><span class="sxs-lookup"><span data-stu-id="3c09c-163">**/l**[**anguage**]**:***language*</span></span>|<span data-ttu-id="3c09c-164">Задает используемый язык программирования.</span><span class="sxs-lookup"><span data-stu-id="3c09c-164">Specifies the programming language to use.</span></span> <span data-ttu-id="3c09c-165">Доступный выбор: `CS` (C#, по умолчанию), `VB` (Visual Basic), `JS` (JScript) или `VJS` (Visual J#).</span><span class="sxs-lookup"><span data-stu-id="3c09c-165">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="3c09c-166">Также можно указать полное имя класса, реализующего <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3c09c-166">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|  
|<span data-ttu-id="3c09c-167">**/n**[**amespace**]**:***namespace*</span><span class="sxs-lookup"><span data-stu-id="3c09c-167">**/n**[**amespace**]**:***namespace*</span></span>|<span data-ttu-id="3c09c-168">Определяет пространство имен среды выполнения для создаваемых типов.</span><span class="sxs-lookup"><span data-stu-id="3c09c-168">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="3c09c-169">Пространство имен по умолчанию — `Schemas`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-169">The default namespace is `Schemas`.</span></span>|  
|<span data-ttu-id="3c09c-170">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="3c09c-170">**/nologo**</span></span>|<span data-ttu-id="3c09c-171">Отключает баннер.</span><span class="sxs-lookup"><span data-stu-id="3c09c-171">Suppresses the banner.</span></span>|  
|<span data-ttu-id="3c09c-172">**/order**</span><span class="sxs-lookup"><span data-stu-id="3c09c-172">**/order**</span></span>|<span data-ttu-id="3c09c-173">Создает явные идентификаторы порядка для всех примитивных членов.</span><span class="sxs-lookup"><span data-stu-id="3c09c-173">Generates explicit order identifiers on all particle members.</span></span>|  
|<span data-ttu-id="3c09c-174">**/o[ut]:** *имя_каталога*</span><span class="sxs-lookup"><span data-stu-id="3c09c-174">**/o[ut]:** *directoryName*</span></span>|<span data-ttu-id="3c09c-175">Задает выходной каталог, в котором следует разместить файлы.</span><span class="sxs-lookup"><span data-stu-id="3c09c-175">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="3c09c-176">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-176">The default is the current directory.</span></span>|  
|<span data-ttu-id="3c09c-177">**/u**[**ri**]**:***uri*</span><span class="sxs-lookup"><span data-stu-id="3c09c-177">**/u**[**ri**]**:***uri*</span></span>|<span data-ttu-id="3c09c-178">Определяет универсальный код ресурса (URI) для элементов схемы, для которого создается код.</span><span class="sxs-lookup"><span data-stu-id="3c09c-178">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="3c09c-179">Этот универсальный код ресурса, если имеется, применяется ко всем элементам, заданным параметром `/element`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-179">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|  
  
## <a name="dll-and-exe-file-options"></a><span data-ttu-id="3c09c-180">Параметры файлов DLL и EXE</span><span class="sxs-lookup"><span data-stu-id="3c09c-180">DLL and EXE File Options</span></span>  
  
|<span data-ttu-id="3c09c-181">Параметр</span><span class="sxs-lookup"><span data-stu-id="3c09c-181">Option</span></span>|<span data-ttu-id="3c09c-182">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-182">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3c09c-183">**/t**[**тип**] **: *** typename*</span><span class="sxs-lookup"><span data-stu-id="3c09c-183">**/t**[**ype**]**:***typename*</span></span>|<span data-ttu-id="3c09c-184">Задает имя типа, для которого следует создать схему.</span><span class="sxs-lookup"><span data-stu-id="3c09c-184">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="3c09c-185">Можно указать несколько аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="3c09c-185">You can specify multiple type arguments.</span></span> <span data-ttu-id="3c09c-186">Если *имя_типа* не указывает пространство имен, Xsd.exe сопоставляет все типы в сборке с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="3c09c-186">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="3c09c-187">Если *имя_типа* задает пространство имен, сопоставляется только этот тип.</span><span class="sxs-lookup"><span data-stu-id="3c09c-187">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="3c09c-188">Если *имя_типа* заканчивается знаком звездочки (\*), средство сопоставляет все типы, которые начинаются со строки, предшествующей знаку звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="3c09c-188">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="3c09c-189">Если параметр `/type` не задан, Xsd.exe создает схемы для всех типов в сборке.</span><span class="sxs-lookup"><span data-stu-id="3c09c-189">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c09c-190">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c09c-190">Remarks</span></span>  
 <span data-ttu-id="3c09c-191">В следующей таблице показаны операции, выполняемые Xsd.exe.</span><span class="sxs-lookup"><span data-stu-id="3c09c-191">The following table shows the operations that Xsd.exe performs.</span></span>  
  
 <span data-ttu-id="3c09c-192">XDR в XSD</span><span class="sxs-lookup"><span data-stu-id="3c09c-192">XDR to XSD</span></span>  
 <span data-ttu-id="3c09c-193">Создает схему XML из файла схемы XDR.</span><span class="sxs-lookup"><span data-stu-id="3c09c-193">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="3c09c-194">XDR является более ранним форматом схемы, основанной на XML.</span><span class="sxs-lookup"><span data-stu-id="3c09c-194">XDR is an early XML-based schema format.</span></span>  
  
 <span data-ttu-id="3c09c-195">XML в XSD</span><span class="sxs-lookup"><span data-stu-id="3c09c-195">XML to XSD</span></span>  
 <span data-ttu-id="3c09c-196">Создает схему XML из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="3c09c-196">Generates an XML schema from an XML file.</span></span>  
  
 <span data-ttu-id="3c09c-197">XSD в DataSet</span><span class="sxs-lookup"><span data-stu-id="3c09c-197">XSD to DataSet</span></span>  
 <span data-ttu-id="3c09c-198">Создает классы CLR <xref:System.Data.DataSet> из файла схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-198">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="3c09c-199">Создаваемые классы представляют собой объектную модель с широкими функциональными возможностями для обычных данных XML.</span><span class="sxs-lookup"><span data-stu-id="3c09c-199">The generated classes provide a rich object model for regular XML data.</span></span>  
  
 <span data-ttu-id="3c09c-200">XSD в классы</span><span class="sxs-lookup"><span data-stu-id="3c09c-200">XSD to Classes</span></span>  
 <span data-ttu-id="3c09c-201">Создает классы среды выполнения из файла схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="3c09c-201">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="3c09c-202">Созданные классы можно использовать совместно с <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> для чтения и записи кода XML, соответствующего схеме.</span><span class="sxs-lookup"><span data-stu-id="3c09c-202">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>  
  
 <span data-ttu-id="3c09c-203">Классы в XSD</span><span class="sxs-lookup"><span data-stu-id="3c09c-203">Classes to XSD</span></span>  
 <span data-ttu-id="3c09c-204">Создает схему XML из типа или типов в файле сборки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3c09c-204">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="3c09c-205">Созданная схема определяет формат XML, используемый `System.Xml.Serialization.XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-205">The generated schema defines the XML format used by `System.Xml.Serialization.XmlSerializer`.</span></span>  
  
 <span data-ttu-id="3c09c-206">Xsd.exe позволяет управлять только схемами XML, которые соответствуют языку определения схемы XML (XSD), предложенному консорциумом World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="3c09c-206">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="3c09c-207">Дополнительные сведения о предложении определения схемы XML или стандарт XML см. в разделе http://w3.org.</span><span class="sxs-lookup"><span data-stu-id="3c09c-207">For more information on the XML Schema Definition proposal or the XML standard, see http://w3.org.</span></span>  
  
## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="3c09c-208">Установка параметров с помощью XML-файла</span><span class="sxs-lookup"><span data-stu-id="3c09c-208">Setting Options with an XML File</span></span>  
 <span data-ttu-id="3c09c-209">С помощью параметра `/parameters` можно задать один XML-файл, который содержит различные параметры.</span><span class="sxs-lookup"><span data-stu-id="3c09c-209">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="3c09c-210">Задаваемые параметры зависят от способа использования инструмента XSD.exe.</span><span class="sxs-lookup"><span data-stu-id="3c09c-210">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="3c09c-211">Варианты включают в себя создание схем, файлов кода или создание файлов кода, содержащих функции `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-211">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="3c09c-212">Например, можно задать элемент `<assembly\>` как имя исполняемого файла (расширение EXE) или файла библиотеки типов (расширение DLL) при создании схемы, но не при создании файла кода.</span><span class="sxs-lookup"><span data-stu-id="3c09c-212">For example, you can set the `<assembly\>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="3c09c-213">В следующем примере XML показано, как использовать элемент `<generateSchemas\>` с указанным исполняемым файлом:</span><span class="sxs-lookup"><span data-stu-id="3c09c-213">The following XML shows how to use the `<generateSchemas\>` element with a specified executable:</span></span>  
  
```xml  
<!-- This is in a file named GenerateSchemas.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <assembly>ConsoleApplication1.exe</assembly>  
</generateSchemas>  
</xsd>  
```  
  
 <span data-ttu-id="3c09c-214">Если предыдущий XML содержится в файле с именем GenerateSchemas.xml, используйте параметр `/parameters`, введя следующий текст в командной строке и нажав клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3c09c-214">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing ENTER:</span></span>  
  
 `xsd /p:GenerateSchemas.xml`  
  
 <span data-ttu-id="3c09c-215">С другой стороны, при создании схемы для одного типа, найденного в сборке, можно использовать следующий XML:</span><span class="sxs-lookup"><span data-stu-id="3c09c-215">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>  
  
```xml  
<!-- This is in a file named GenerateSchemaFromType.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <type>IDItems</type>  
</generateSchemas>  
</xsd>  
```  
  
 <span data-ttu-id="3c09c-216">Но чтобы использовать предыдущий код, в командной строке следует также указать имя сборки.</span><span class="sxs-lookup"><span data-stu-id="3c09c-216">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="3c09c-217">В командной строке введите следующую команду (допустим, имя XML-файла - GenerateSchemaFromType.xml):</span><span class="sxs-lookup"><span data-stu-id="3c09c-217">Type the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>  
  
 `xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe`  
  
 <span data-ttu-id="3c09c-218">Для элемента `\<generateSchemas>` следует указать только один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3c09c-218">You must specify only one of the following options for the `\<generateSchemas>` element.</span></span>  
  
|<span data-ttu-id="3c09c-219">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c09c-219">Element</span></span>|<span data-ttu-id="3c09c-220">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-220">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c09c-221">\<assembly></span><span class="sxs-lookup"><span data-stu-id="3c09c-221">\<assembly></span></span>|<span data-ttu-id="3c09c-222">Определяет сборку, из которой создается схема.</span><span class="sxs-lookup"><span data-stu-id="3c09c-222">Specifies an assembly to generate the schema from.</span></span>|  
|<span data-ttu-id="3c09c-223">\<type></span><span class="sxs-lookup"><span data-stu-id="3c09c-223">\<type></span></span>|<span data-ttu-id="3c09c-224">Определяет тип, найденный в сборке, для которого создается схема.</span><span class="sxs-lookup"><span data-stu-id="3c09c-224">Specifies a type found in an assembly to generate a schema for.</span></span>|  
|<span data-ttu-id="3c09c-225">\<xml></span><span class="sxs-lookup"><span data-stu-id="3c09c-225">\<xml></span></span>|<span data-ttu-id="3c09c-226">Задает XML-файл, для которого создается схема.</span><span class="sxs-lookup"><span data-stu-id="3c09c-226">Specifies an XML file to generate a schema for.</span></span>|  
|<span data-ttu-id="3c09c-227">\<xdr></span><span class="sxs-lookup"><span data-stu-id="3c09c-227">\<xdr></span></span>|<span data-ttu-id="3c09c-228">Определяет файл XDR, для которого создается схема.</span><span class="sxs-lookup"><span data-stu-id="3c09c-228">Specifies an XDR file to generate a schema for.</span></span>|  
  
 <span data-ttu-id="3c09c-229">Чтобы создать файл кода, используйте элемент `<generateClasses\>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-229">To generate a code file, use the `<generateClasses\>` element.</span></span> <span data-ttu-id="3c09c-230">В следующем примере создается файл кода.</span><span class="sxs-lookup"><span data-stu-id="3c09c-230">The following example generates a code file.</span></span> <span data-ttu-id="3c09c-231">Обратите внимание, что также отображаются два атрибута, с помощью которых можно задать язык программирования и пространство имен создаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="3c09c-231">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>  
  
```xml  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>  
</xsd>  
<!-- You must supply an .xsd file when typing in the command line.-->  
<!-- For example: xsd /p:genClasses mySchema.xsd -->  
```  
  
 <span data-ttu-id="3c09c-232">Параметры, которые можно задать для элемента `\<generateClasses>`, включают в себя следующие.</span><span class="sxs-lookup"><span data-stu-id="3c09c-232">Options you can set for the `\<generateClasses>` element include the following.</span></span>  
  
|<span data-ttu-id="3c09c-233">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c09c-233">Element</span></span>|<span data-ttu-id="3c09c-234">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-234">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c09c-235">\<element></span><span class="sxs-lookup"><span data-stu-id="3c09c-235">\<element></span></span>|<span data-ttu-id="3c09c-236">Определяет элемент в файле XSD, для которого создается код.</span><span class="sxs-lookup"><span data-stu-id="3c09c-236">Specifies an element in the .xsd file to generate code for.</span></span>|  
|<span data-ttu-id="3c09c-237">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3c09c-237">\<schemaImporterExtensions></span></span>|<span data-ttu-id="3c09c-238">Определяет тип, унаследованный от класса <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>.</span><span class="sxs-lookup"><span data-stu-id="3c09c-238">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|  
|<span data-ttu-id="3c09c-239">\<schema></span><span class="sxs-lookup"><span data-stu-id="3c09c-239">\<schema></span></span>|<span data-ttu-id="3c09c-240">Определяет файл схемы XML, для которой создается код.</span><span class="sxs-lookup"><span data-stu-id="3c09c-240">Specifies a XML Schema file to generate code for.</span></span>  <span data-ttu-id="3c09c-241">С помощью нескольких элементов \<schema> можно задать несколько файлов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="3c09c-241">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|  
  
 <span data-ttu-id="3c09c-242">В следующей таблице представлены атрибуты, которые также можно использовать с элементом `<generateClasses\>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-242">The following table shows the attributes that can also be used with the `<generateClasses\>` element.</span></span>  
  
|<span data-ttu-id="3c09c-243">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3c09c-243">Attribute</span></span>|<span data-ttu-id="3c09c-244">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-244">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c09c-245">язык</span><span class="sxs-lookup"><span data-stu-id="3c09c-245">language</span></span>|<span data-ttu-id="3c09c-246">Задает используемый язык программирования.</span><span class="sxs-lookup"><span data-stu-id="3c09c-246">Specifies the programming language to use.</span></span> <span data-ttu-id="3c09c-247">Доступный выбор: `CS` (C#, по умолчанию), `VB` (Visual Basic), `JS` (JScript) или `VJS` (Visual J#).</span><span class="sxs-lookup"><span data-stu-id="3c09c-247">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="3c09c-248">Также можно указать полное имя класса, реализующего <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="3c09c-248">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|  
|<span data-ttu-id="3c09c-249">namespace</span><span class="sxs-lookup"><span data-stu-id="3c09c-249">namespace</span></span>|<span data-ttu-id="3c09c-250">Задает пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="3c09c-250">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="3c09c-251">Пространство имен должно соответствовать стандартам CLR (например, отсутствие пробелов или обратной косой черты).</span><span class="sxs-lookup"><span data-stu-id="3c09c-251">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|  
|<span data-ttu-id="3c09c-252">параметры</span><span class="sxs-lookup"><span data-stu-id="3c09c-252">options</span></span>|<span data-ttu-id="3c09c-253">Одно из следующих значений: `none`, `properties` (создает свойства вместо открытых полей), `order` или `enableDataBinding` (см. параметры `/order` и `/enableDataBinding` в предыдущем разделе параметров файла XSD).</span><span class="sxs-lookup"><span data-stu-id="3c09c-253">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|  
  
 <span data-ttu-id="3c09c-254">Также предусмотрена возможность управления созданием кода `DataSet` с использованием элемента `<generateDataSets\>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-254">You can also control how `DataSet` code is generated by using the `<generateDataSets\>` element.</span></span> <span data-ttu-id="3c09c-255">Приведенный ниже XML-код указывает, что созданный код использует структуры `DataSet` (например, класс <xref:System.Data.DataTable>) для создания кода Visual Basic для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="3c09c-255">The following XML specifies that the generated codeuses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="3c09c-256">Созданные структуры DataSet поддерживают запросы LINQ.</span><span class="sxs-lookup"><span data-stu-id="3c09c-256">The generated DataSet structures will support LINQ queries.</span></span>  
  
 `<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>`  
  
 `<generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>`  
  
 `</generateDataSet>`  
  
 `</xsd>`  
  
 <span data-ttu-id="3c09c-257">Параметры, которые можно задать для элемента `<generateDataSet\>`, включают в себя следующие.</span><span class="sxs-lookup"><span data-stu-id="3c09c-257">Options you can set for the `<generateDataSet\>` element include the following.</span></span>  
  
|<span data-ttu-id="3c09c-258">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c09c-258">Element</span></span>|<span data-ttu-id="3c09c-259">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-259">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c09c-260">\<schema></span><span class="sxs-lookup"><span data-stu-id="3c09c-260">\<schema></span></span>|<span data-ttu-id="3c09c-261">Определяет файл схемы XML, для которой создается код.</span><span class="sxs-lookup"><span data-stu-id="3c09c-261">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="3c09c-262">С помощью нескольких элементов \<schema> можно задать несколько файлов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="3c09c-262">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|  
  
 <span data-ttu-id="3c09c-263">В следующей таблице представлены атрибуты, которые можно использовать с элементом `<generateDataSet\>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-263">The following table shows the attributes that can be used with the `<generateDataSet\>` element.</span></span>  
  
|<span data-ttu-id="3c09c-264">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3c09c-264">Attribute</span></span>|<span data-ttu-id="3c09c-265">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-265">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c09c-266">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="3c09c-266">enableLinqDataSet</span></span>|<span data-ttu-id="3c09c-267">Указывает, что созданный набор данных можно запросить с помощью LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="3c09c-267">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="3c09c-268">Значением по умолчанию является false.</span><span class="sxs-lookup"><span data-stu-id="3c09c-268">The default value is false.</span></span>|  
|<span data-ttu-id="3c09c-269">язык</span><span class="sxs-lookup"><span data-stu-id="3c09c-269">language</span></span>|<span data-ttu-id="3c09c-270">Задает используемый язык программирования.</span><span class="sxs-lookup"><span data-stu-id="3c09c-270">Specifies the programming language to use.</span></span> <span data-ttu-id="3c09c-271">Доступный выбор: `CS` (C#, по умолчанию), `VB` (Visual Basic), `JS` (JScript) или `VJS` (Visual J#).</span><span class="sxs-lookup"><span data-stu-id="3c09c-271">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="3c09c-272">Также можно указать полное имя класса, реализующего <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="3c09c-272">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|  
|<span data-ttu-id="3c09c-273">namespace</span><span class="sxs-lookup"><span data-stu-id="3c09c-273">namespace</span></span>|<span data-ttu-id="3c09c-274">Задает пространство имен созданного кода.</span><span class="sxs-lookup"><span data-stu-id="3c09c-274">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="3c09c-275">Пространство имен должно соответствовать стандартам CLR (например, отсутствие пробелов или обратной косой черты).</span><span class="sxs-lookup"><span data-stu-id="3c09c-275">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|  
  
 <span data-ttu-id="3c09c-276">Существуют атрибуты, которые можно задать для элемента верхнего уровня `<xsd\>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-276">There are attributes that you can set on the top level `<xsd\>` element.</span></span> <span data-ttu-id="3c09c-277">Эти параметры можно использовать с любым из дочерних элементов (`<generateSchemas\>`, `<generateClasses\>` или `<generateDataSet\>`).</span><span class="sxs-lookup"><span data-stu-id="3c09c-277">These options can be used with any of the child elements (`<generateSchemas\>`, `<generateClasses\>` or `<generateDataSet\>`).</span></span> <span data-ttu-id="3c09c-278">Следующий код XML создает код для элемента с именем "IDItems" в выходном каталоге с именем "MyOutputDirectory".</span><span class="sxs-lookup"><span data-stu-id="3c09c-278">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>  
  
```xml  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>  
<generateClasses>  
<element>IDItems</element>  
</generateClasses>  
</xsd>  
```  
  
 <span data-ttu-id="3c09c-279">В следующей таблице представлены атрибуты, которые также можно использовать с элементом `\<xsd>`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-279">The following table shows the attributes that can also be used with the `\<xsd>` element.</span></span>  
  
|<span data-ttu-id="3c09c-280">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3c09c-280">Attribute</span></span>|<span data-ttu-id="3c09c-281">Описание</span><span class="sxs-lookup"><span data-stu-id="3c09c-281">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c09c-282">результат</span><span class="sxs-lookup"><span data-stu-id="3c09c-282">output</span></span>|<span data-ttu-id="3c09c-283">Имя каталога, в который сохраняется созданная схема или файл кода.</span><span class="sxs-lookup"><span data-stu-id="3c09c-283">The name of a directory where the generated schema or code file will be placed.</span></span>|  
|<span data-ttu-id="3c09c-284">nologo</span><span class="sxs-lookup"><span data-stu-id="3c09c-284">nologo</span></span>|<span data-ttu-id="3c09c-285">Отключает баннер.</span><span class="sxs-lookup"><span data-stu-id="3c09c-285">Suppresses the banner.</span></span> <span data-ttu-id="3c09c-286">Задайте `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-286">Set to `true` or `false`.</span></span>|  
|<span data-ttu-id="3c09c-287">help</span><span class="sxs-lookup"><span data-stu-id="3c09c-287">help</span></span>|<span data-ttu-id="3c09c-288">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="3c09c-288">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="3c09c-289">Задайте `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="3c09c-289">Set to `true` or `false`.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="3c09c-290">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c09c-290">Examples</span></span>  
 <span data-ttu-id="3c09c-291">Следующая команда создает схему XML из `myFile.xdr` и сохраняет ее в текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-291">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>  
  
```  
xsd myFile.xdr   
```  
  
 <span data-ttu-id="3c09c-292">Следующая команда создает схему XML из `myFile.xml` и сохраняет ее в указанный каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-292">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>  
  
```  
xsd myFile.xml /outputdir:myOutputDir  
```  
  
 <span data-ttu-id="3c09c-293">Следующая команда создает набор данных, соответствующий определенной схеме на языке C# и сохраняет его как `XSDSchemaFile.cs` в текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-293">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>  
  
```  
xsd /dataset /language:CS XSDSchemaFile.xsd  
```  
  
 <span data-ttu-id="3c09c-294">Следующая команда создает схемы XML для всех типов в сборке `myAssembly.dll` и сохраняет их как `schema0.xsd` в текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="3c09c-294">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>  
  
```  
xsd myAssembly.dll    
```  
  
## <a name="see-also"></a><span data-ttu-id="3c09c-295">См. также</span><span class="sxs-lookup"><span data-stu-id="3c09c-295">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>  
 <span data-ttu-id="3c09c-296">[Инструменты](../../../docs/framework/tools/index.md)    </span><span class="sxs-lookup"><span data-stu-id="3c09c-296">[Tools](../../../docs/framework/tools/index.md)    </span></span>  
 [<span data-ttu-id="3c09c-297">Командные строки</span><span class="sxs-lookup"><span data-stu-id="3c09c-297">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)  
 [<span data-ttu-id="3c09c-298">Общие сведения о LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="3c09c-298">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="3c09c-299">Запрос к типизированным объектам DataSet</span><span class="sxs-lookup"><span data-stu-id="3c09c-299">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [<span data-ttu-id="3c09c-300">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="3c09c-300">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
