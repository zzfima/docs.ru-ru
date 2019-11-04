---
title: Mgmtclassgen.exe (генератор строго типизированных классов управления)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: 5002d7a180e480b0e1d38f1c1180fe565dc5e1dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105023"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="0f515-102">Mgmtclassgen.exe (генератор строго типизированных классов управления)</span><span class="sxs-lookup"><span data-stu-id="0f515-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>
<span data-ttu-id="0f515-103">Генератор классов управления со строгим типом позволяет быстро создавать управляемые классы с ранней привязкой для указанного класса инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="0f515-103">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="0f515-104">Создаваемый класс упрощает код, необходимый для доступа к экземпляру класса WMI.</span><span class="sxs-lookup"><span data-stu-id="0f515-104">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f515-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f515-105">Syntax</span></span>  
  
```console  
mgmtclassgen   
WMIClass [options]   
```  
  
|<span data-ttu-id="0f515-106">Аргумент</span><span class="sxs-lookup"><span data-stu-id="0f515-106">Argument</span></span>|<span data-ttu-id="0f515-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0f515-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0f515-108">*WMIClass*</span><span class="sxs-lookup"><span data-stu-id="0f515-108">*WMIClass*</span></span>|<span data-ttu-id="0f515-109">Класс WMI, для которого создается управляемый класс с ранней привязкой.</span><span class="sxs-lookup"><span data-stu-id="0f515-109">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="0f515-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="0f515-110">Option</span></span>|<span data-ttu-id="0f515-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0f515-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0f515-112">**/l**  *язык*</span><span class="sxs-lookup"><span data-stu-id="0f515-112">**/l**  *language*</span></span>|<span data-ttu-id="0f515-113">Задает язык, на котором создается управляемый класс с ранней привязкой.</span><span class="sxs-lookup"><span data-stu-id="0f515-113">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="0f515-114">В качестве аргумента, задающего язык, можно указать **CS** (C#, используется по умолчанию), **VB** (Visual Basic), **MC** (C++) или **VS** (JScript).</span><span class="sxs-lookup"><span data-stu-id="0f515-114">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="0f515-115">**/m**  *компьютер*</span><span class="sxs-lookup"><span data-stu-id="0f515-115">**/m**  *machine*</span></span>|<span data-ttu-id="0f515-116">Задает компьютер, к которому следует подключиться и на котором находится соответствующий класс WMI.</span><span class="sxs-lookup"><span data-stu-id="0f515-116">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="0f515-117">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0f515-117">The default is the local computer.</span></span>|  
|<span data-ttu-id="0f515-118">**/n**  *path*</span><span class="sxs-lookup"><span data-stu-id="0f515-118">**/n**  *path*</span></span>|<span data-ttu-id="0f515-119">Задает путь к пространству имен WMI, в котором содержится класс WMI.</span><span class="sxs-lookup"><span data-stu-id="0f515-119">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="0f515-120">Если этот параметр не указан, программа создает код для *WMIClass* в пространстве имен по умолчанию **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0f515-120">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="0f515-121">**/o** *пространство_имен_класса*</span><span class="sxs-lookup"><span data-stu-id="0f515-121">**/o**  *classnamespace*</span></span>|<span data-ttu-id="0f515-122">Задает пространство имен .NET, в котором создается класс управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0f515-122">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="0f515-123">Если этот параметр не указан, программа создает пространство имен, используя пространство имен WMI и префикс схемы.</span><span class="sxs-lookup"><span data-stu-id="0f515-123">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="0f515-124">Префикс схемы представляет собой часть имени класса перед знаком подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="0f515-124">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="0f515-125">Например, для класса **Win32_OperatingSystem** в пространстве имен **Root\cimv2** программа создает класс в пространстве имен **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="0f515-125">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="0f515-126">**/p**  *путь_к_файлу*</span><span class="sxs-lookup"><span data-stu-id="0f515-126">**/p**  *filepath*</span></span>|<span data-ttu-id="0f515-127">Задает путь к файлу, в который будет записан созданный код.</span><span class="sxs-lookup"><span data-stu-id="0f515-127">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="0f515-128">Если этот параметр не задан, программа создаст файл в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0f515-128">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="0f515-129">Имена класса и файла, в котором он будет храниться, присваиваются на основе аргумента *WMIClass*.</span><span class="sxs-lookup"><span data-stu-id="0f515-129">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="0f515-130">Имена класса и файла будут совпадать с именем *WMIClass*.</span><span class="sxs-lookup"><span data-stu-id="0f515-130">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="0f515-131">Если *WMIClass* содержит знак подчеркивания, будет использована часть имени класса после этого знака.</span><span class="sxs-lookup"><span data-stu-id="0f515-131">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="0f515-132">Например, если *WMIClass* имеет вид **Win32_LogicalDisk**, созданным классу и файлу будет присвоено имя "logicaldisk".</span><span class="sxs-lookup"><span data-stu-id="0f515-132">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="0f515-133">Если файл с таким именем уже существует, новый файл будет записан поверх старого.</span><span class="sxs-lookup"><span data-stu-id="0f515-133">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="0f515-134">**/pw**  *пароль*</span><span class="sxs-lookup"><span data-stu-id="0f515-134">**/pw**  *password*</span></span>|<span data-ttu-id="0f515-135">Задает пароль, используемый для подключения к компьютеру, заданному в параметре **/m**.</span><span class="sxs-lookup"><span data-stu-id="0f515-135">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="0f515-136">**/u**  *имя_пользователя*</span><span class="sxs-lookup"><span data-stu-id="0f515-136">**/u**  *user name*</span></span>|<span data-ttu-id="0f515-137">Задает имя пользователя, используемое для подключения к компьютеру, заданному в параметре **/m**.</span><span class="sxs-lookup"><span data-stu-id="0f515-137">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="0f515-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="0f515-138">**/?**</span></span>|<span data-ttu-id="0f515-139">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="0f515-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f515-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f515-140">Remarks</span></span>  
 <span data-ttu-id="0f515-141">Программа Mgmtclassgen.exe использует метод <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f515-141">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0f515-142">Поэтому для генерации кода на управляемом языке, отличном от C#, Visual Basic и JScript, можно использовать любой нестандартный поставщик кода.</span><span class="sxs-lookup"><span data-stu-id="0f515-142">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="0f515-143">Следует заметить, что создаваемые классы связаны со схемой, для которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="0f515-143">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="0f515-144">Если базовая схема изменяется, для отображения внесенных изменений в схеме класс следует создать повторно.</span><span class="sxs-lookup"><span data-stu-id="0f515-144">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="0f515-145">В следующей таблице приводится соответствие типов модели CIM WMI и типов данных в создаваемых классах.</span><span class="sxs-lookup"><span data-stu-id="0f515-145">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="0f515-146">Тип CIM</span><span class="sxs-lookup"><span data-stu-id="0f515-146">CIM type</span></span>|<span data-ttu-id="0f515-147">Тип данных создаваемого класса</span><span class="sxs-lookup"><span data-stu-id="0f515-147">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="0f515-148">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="0f515-148">CIM_SINT8</span></span>|<span data-ttu-id="0f515-149">**SByte**</span><span class="sxs-lookup"><span data-stu-id="0f515-149">**SByte**</span></span>|  
|<span data-ttu-id="0f515-150">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="0f515-150">CIM_UINT8</span></span>|<span data-ttu-id="0f515-151">**Byte**</span><span class="sxs-lookup"><span data-stu-id="0f515-151">**Byte**</span></span>|  
|<span data-ttu-id="0f515-152">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="0f515-152">CIM_SINT16</span></span>|<span data-ttu-id="0f515-153">**Int16**</span><span class="sxs-lookup"><span data-stu-id="0f515-153">**Int16**</span></span>|  
|<span data-ttu-id="0f515-154">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="0f515-154">CIM_UINT16</span></span>|<span data-ttu-id="0f515-155">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="0f515-155">**UInt16**</span></span>|  
|<span data-ttu-id="0f515-156">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="0f515-156">CIM_SINT32</span></span>|<span data-ttu-id="0f515-157">**Int32**</span><span class="sxs-lookup"><span data-stu-id="0f515-157">**Int32**</span></span>|  
|<span data-ttu-id="0f515-158">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="0f515-158">SIM_UINT32</span></span>|<span data-ttu-id="0f515-159">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="0f515-159">**UInt32**</span></span>|  
|<span data-ttu-id="0f515-160">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="0f515-160">CIM_SINT64</span></span>|<span data-ttu-id="0f515-161">**Int64**</span><span class="sxs-lookup"><span data-stu-id="0f515-161">**Int64**</span></span>|  
|<span data-ttu-id="0f515-162">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="0f515-162">CIM_UINT64</span></span>|<span data-ttu-id="0f515-163">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="0f515-163">**UInt64**</span></span>|  
|<span data-ttu-id="0f515-164">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="0f515-164">CIM_REAL32</span></span>|<span data-ttu-id="0f515-165">**Single**</span><span class="sxs-lookup"><span data-stu-id="0f515-165">**Single**</span></span>|  
|<span data-ttu-id="0f515-166">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="0f515-166">CIM_REAL64</span></span>|<span data-ttu-id="0f515-167">**Double**</span><span class="sxs-lookup"><span data-stu-id="0f515-167">**Double**</span></span>|  
|<span data-ttu-id="0f515-168">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="0f515-168">CIM_BOOLEAN</span></span>|<span data-ttu-id="0f515-169">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0f515-169">**Boolean**</span></span>|  
|<span data-ttu-id="0f515-170">CIM_String</span><span class="sxs-lookup"><span data-stu-id="0f515-170">CIM_String</span></span>|<span data-ttu-id="0f515-171">**String**</span><span class="sxs-lookup"><span data-stu-id="0f515-171">**String**</span></span>|  
|<span data-ttu-id="0f515-172">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="0f515-172">CIM_DATETIME</span></span>|<span data-ttu-id="0f515-173">**DateTime** или **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="0f515-173">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="0f515-174">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="0f515-174">CIM_REFERENCE</span></span>|<span data-ttu-id="0f515-175">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="0f515-175">**ManagementPath**</span></span>|  
|<span data-ttu-id="0f515-176">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="0f515-176">CIM_CHAR16</span></span>|<span data-ttu-id="0f515-177">**Char**</span><span class="sxs-lookup"><span data-stu-id="0f515-177">**Char**</span></span>|  
|<span data-ttu-id="0f515-178">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="0f515-178">CIM_OBJECT</span></span>|<span data-ttu-id="0f515-179">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="0f515-179">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="0f515-180">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="0f515-180">CIM_IUNKNOWN</span></span>|<span data-ttu-id="0f515-181">**Объект**</span><span class="sxs-lookup"><span data-stu-id="0f515-181">**Object**</span></span>|  
|<span data-ttu-id="0f515-182">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f515-182">CIM_ARRAY</span></span>|<span data-ttu-id="0f515-183">Массив указанных выше объектов</span><span class="sxs-lookup"><span data-stu-id="0f515-183">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="0f515-184">Отметим следующие особенности процесса создания классов WMI.</span><span class="sxs-lookup"><span data-stu-id="0f515-184">Note the following behaviors when you generate a WMI class:</span></span>  
  
- <span data-ttu-id="0f515-185">Стандартное открытое свойство или метод может иметь имя, совпадающее с именем существующего свойства или метода.</span><span class="sxs-lookup"><span data-stu-id="0f515-185">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="0f515-186">В этом случае программа изменит имя свойства или метода в создаваемом классе, чтобы избежать конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="0f515-186">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="0f515-187">Свойство или метод создаваемого класса может иметь имя, совпадающее с зарезервированным ключевым словом используемого языка программирования.</span><span class="sxs-lookup"><span data-stu-id="0f515-187">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="0f515-188">В этом случае программа изменит имя свойства или метода в создаваемом классе, чтобы избежать конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="0f515-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="0f515-189">В WMI квалификаторами называются модификаторы, которые содержат информацию, описывающую класс, экземпляр, свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="0f515-189">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="0f515-190">В WMI для описания свойств создаваемого класса используются стандартные квалификаторы, такие как **Read**, **Write** и **Key**.</span><span class="sxs-lookup"><span data-stu-id="0f515-190">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="0f515-191">Например, свойство, измененное квалификатором **Read**, определяется только совместно со свойством метода доступа **get** в создаваемом классе.</span><span class="sxs-lookup"><span data-stu-id="0f515-191">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="0f515-192">Так как свойство, помеченное квалификатором **Read**, предназначено только для чтения, метод доступа **set** не определяется.</span><span class="sxs-lookup"><span data-stu-id="0f515-192">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
- <span data-ttu-id="0f515-193">Числовое свойство можно изменить с помощью квалификаторов **Values** и **ValueMaps**, которые указывают, что свойство может принимать только указанные допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="0f515-193">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="0f515-194">Перечисление создается на основе квалификаторов **Values** и **ValueMaps**, а свойство сопоставляется с этим перечислением.</span><span class="sxs-lookup"><span data-stu-id="0f515-194">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
- <span data-ttu-id="0f515-195">Класс, который может иметь только один экземпляр, в WMI называется одноэлементным.</span><span class="sxs-lookup"><span data-stu-id="0f515-195">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="0f515-196">Таким образом, конструктор без параметров для отдельного класса инициализирует класс в единственном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="0f515-196">Therefore, the parameterless constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
- <span data-ttu-id="0f515-197">У класса WMI могут быть свойства, которые являются объектами.</span><span class="sxs-lookup"><span data-stu-id="0f515-197">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="0f515-198">При создании класса со строгим типом для данного типа класса WMI следует по возможности создавать классы со строгими типами для типов свойств внедренных объектов.</span><span class="sxs-lookup"><span data-stu-id="0f515-198">When you generate a strongly-typed class for this type of WMI class, you should consider generating strongly-typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="0f515-199">Благодаря этому станет возможен доступ к внедренным объектам в режиме строгой типизации.</span><span class="sxs-lookup"><span data-stu-id="0f515-199">This will allow you to access the embedded objects in a strongly-typed manner.</span></span> <span data-ttu-id="0f515-200">Следует заметить, что создаваемый код не всегда может определить тип внедренного объекта.</span><span class="sxs-lookup"><span data-stu-id="0f515-200">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="0f515-201">В этом случае в созданном коде будет создан комментарий с уведомлением об этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="0f515-201">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="0f515-202">Обнаружив такое уведомление, можно изменить созданный код, приписав свойство другому созданному классу.</span><span class="sxs-lookup"><span data-stu-id="0f515-202">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
- <span data-ttu-id="0f515-203">В WMI значение данных типа CIM_DATETIME может быть представлено как в виде определенной даты и времени, так и в виде временного интервала.</span><span class="sxs-lookup"><span data-stu-id="0f515-203">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="0f515-204">Если значение данных представляет собой время и дату, в созданном классе ему будет соответствовать тип данных **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="0f515-204">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="0f515-205">Если значение данных представляет собой временной интервал, в созданном классе ему будет соответствовать тип данных **TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="0f515-205">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="0f515-206">Управляемые классы со строгим типом можно создавать также с помощью Server Explorer Management Extension в Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="0f515-206">You can alternately generate a strongly-typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="0f515-207">Дополнительные сведения о WMI см. в разделе **Инструментарий управления Windows** в документации по продукту Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="0f515-207">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f515-208">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f515-208">Examples</span></span>  
 <span data-ttu-id="0f515-209">При выполнении следующей команды создается управляемый класс на языке C# для класса WMI **Win32_LogicalDisk** в пространстве имен **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0f515-209">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="0f515-210">Программа записывает управляемый класс в исходный файл, расположенный в "c:\disk.cs", в пространстве имен **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="0f515-210">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="0f515-211">В следующем примере кода показано, как использовать созданный класс в программе.</span><span class="sxs-lookup"><span data-stu-id="0f515-211">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="0f515-212">Сначала экземпляр класса перечисляется, и к нему печатается путь.</span><span class="sxs-lookup"><span data-stu-id="0f515-212">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="0f515-213">Затем создается экземпляр инициализируемого класса с экземпляром WMI.</span><span class="sxs-lookup"><span data-stu-id="0f515-213">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="0f515-214">`Process` — это класс, созданный для **Win32_Process**, а `LogicalDisk` — это класс, созданный для **Win32_LogicalDisk** в пространстве имен **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="0f515-214">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App     
   Public Shared Sub Main()        
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process     
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f515-215">См. также</span><span class="sxs-lookup"><span data-stu-id="0f515-215">See also</span></span>

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [<span data-ttu-id="0f515-216">Инструменты</span><span class="sxs-lookup"><span data-stu-id="0f515-216">Tools</span></span>](index.md)
- [<span data-ttu-id="0f515-217">Командные строки</span><span class="sxs-lookup"><span data-stu-id="0f515-217">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
