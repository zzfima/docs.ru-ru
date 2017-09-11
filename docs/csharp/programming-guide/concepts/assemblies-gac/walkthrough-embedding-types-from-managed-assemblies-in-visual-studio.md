---
title: "Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7b003e76229a06883adc22f933f08663330f0c9d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="1e6fa-102">Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="1e6fa-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="1e6fa-103">Внедряя сведения о типе из управляемой сборки со строгим именем, можно свободно объединять типы в приложении, делая версию независимой.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="1e6fa-104">Это означает, что в программе можно использовать типы из нескольких версий управляемой библиотеки, т. е. необходимость компилировать каждую версию отдельно отпадает.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="1e6fa-105">Внедрение типов часто используется с COM-взаимодействием, например в приложениях, использующих объекты автоматизации из Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="1e6fa-106">Сведения о типе внедрения позволяют одной и той же сборке программы работать с различными версиями Microsoft Office на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="1e6fa-107">Тем не менее внедрение типа можно также использовать с полностью управляемым решением.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="1e6fa-108">Сведения о типе можно внедрить из сборки, имеющей следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="1e6fa-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="1e6fa-109">Сборка предоставляет по крайней мере один открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="1e6fa-110">Внедренные интерфейсы снабжаются аннотацией с указанием атрибута `ComImport` и атрибута `Guid` (уникальный GUID).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="1e6fa-111">Сборка снабжается аннотацией с указанием атрибута `ImportedFromTypeLib` или атрибута `PrimaryInteropAssembly`, а также атрибута сборки `Guid`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="1e6fa-112">(По умолчанию шаблоны проектов Visual C# включают атрибут сборки `Guid`.)</span><span class="sxs-lookup"><span data-stu-id="1e6fa-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="1e6fa-113">После того как открытые интерфейсы, доступные для внедрения, будут указаны, можно создать реализующие их классы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="1e6fa-114">Во время разработки клиентская программа встраивает сведения о типе для этих интерфейсов, ссылаясь на сборку, содержащую открытые интерфейсы и присваивая свойству `Embed Interop Types` ссылки значение `True`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="1e6fa-115">Это эквивалентно использованию компилятора командной строки и ссылки на сборку с помощью параметра компилятора `/link`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="1e6fa-116">После этого клиентская программа может загружать экземпляры объектов среды выполнения, типизированные как указанные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="1e6fa-117">При создании новой версии сборки среды выполнения со строгим именем повторная компиляция клиентской программы с обновленной сборкой среды выполнения не требуется.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="1e6fa-118">Клиентская программа продолжает работать с той версией сборки среды выполнения, которая ей доступна, используя сведения о внедренном типе для открытых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="1e6fa-119">Поскольку основной функцией внедрения типа является поддержка внедрения сведений о типе из сборок COM-взаимодействия, при внедрении сведений о типе в полностью управляемое решение применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="1e6fa-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="1e6fa-120">Внедряются только атрибуты, характерные для COM-взаимодействия; другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="1e6fa-121">Если тип включает универсальные параметры внедренного типа, использовать этот тип как границу сборки нельзя.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="1e6fa-122">Граница сборки пересекается, например, при вызове метода из другой сборки или выведении типа из типа, определенного в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="1e6fa-123">Константы не внедряются.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="1e6fa-124">Класс <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> не поддерживает использование внедренного типа в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="1e6fa-125">Для поддержки внедренного типа в качестве ключа можно реализовать свой собственный тип словаря.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="1e6fa-126">В этом пошаговом руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1e6fa-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="1e6fa-127">Создайте сборку со строгим именем и открытым интерфейсом, содержащим сведения о типе, который может быть внедрен.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="1e6fa-128">Создайте сборку среды выполнения со строгим именем, реализующую открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="1e6fa-129">Создайте клиентскую программу, внедряющую сведения о типе из открытого интерфейса и создающую экземпляр класса из сборки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="1e6fa-130">Внесите изменения и создайте сборку среды выполнения заново.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="1e6fa-131">Запустите клиентскую программу, чтобы увидеть, что новая версия сборки среды выполнения позволяет обойтись без повторной компиляции клиентской программы.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="1e6fa-132">Создание интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6fa-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="1e6fa-133">Создание проекта интерфейса для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="1e6fa-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="1e6fa-134">В Visual Studio откройте меню **Файл**, выберите команду **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1e6fa-135">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1e6fa-136">Выберите **Библиотеки классов** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="1e6fa-137">В поле **Имя** введите `TypeEquivalenceInterface` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="1e6fa-138">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1e6fa-139">В **обозревателе решений** щелкните правой кнопкой мыши файл Class1.cs и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="1e6fa-140">Измените имя файла на `ISampleInterface.cs` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="1e6fa-141">При переименовании файла класс также будет переименован в `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="1e6fa-142">Этот класс будет представлять открытый интерфейс для класса.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="1e6fa-143">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="1e6fa-144">Перейдите на вкладку **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-144">Click the the **Build** tab.</span></span> <span data-ttu-id="1e6fa-145">Укажите выходной путь к местоположению, существующему на компьютере разработчика, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="1e6fa-146">Это расположение также пригодится при последующей работе с данным пошаговым руководством.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="1e6fa-147">Не закрывая окно редактирования свойств проекта, откройте вкладку **Подписывание**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="1e6fa-148">Выберите параметр **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="1e6fa-149">В списке **Выберите файл ключа строгого имени** выберите **<Создать...>**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="1e6fa-150">В поле **Имя файла ключа** введите `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="1e6fa-151">Снимите флажок **Защитить файл ключа паролем**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="1e6fa-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1e6fa-153">Откройте файл ISampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-153">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="1e6fa-154">Добавьте следующий код в файл класса ISampleInterface, чтобы создать интерфейс ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="1e6fa-155">В меню **Сервис** выберите пункт **Создать GUID**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-155">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="1e6fa-156">В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-156">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="1e6fa-157">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-157">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="1e6fa-158">В атрибуте `Guid` удалите пример GUID и вставьте GUID, скопированный из диалогового окна **Создание GUID**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-158">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="1e6fa-159">Удалите фигурные скобки ({}) из скопированного GUID.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-159">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="1e6fa-160">В **обозревателе решений** разверните папку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-160">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="1e6fa-161">Дважды щелкните файл AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-161">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="1e6fa-162">Добавьте в файл следующий атрибут.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-162">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="1e6fa-163">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-163">Save the file.</span></span>  
  
10. <span data-ttu-id="1e6fa-164">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-164">Save the project.</span></span>  
  
11. <span data-ttu-id="1e6fa-165">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-165">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="1e6fa-166">DLL-файл библиотеки классов компилируется и сохраняется по указанному выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-166">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="1e6fa-167">Создание класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1e6fa-167">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="1e6fa-168">Создание проекта среды выполнения для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="1e6fa-168">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="1e6fa-169">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-169">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1e6fa-170">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-170">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1e6fa-171">Выберите **Библиотеки классов** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-171">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="1e6fa-172">В поле **Имя** введите `TypeEquivalenceRuntime` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-172">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="1e6fa-173">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-173">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1e6fa-174">В **обозревателе решений** щелкните правой кнопкой мыши файл Class1.cs и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-174">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="1e6fa-175">Измените имя файла на `SampleClass.cs` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-175">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="1e6fa-176">При переименовании файла класс также будет переименован в `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-176">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="1e6fa-177">Этот класс реализует интерфейс `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-177">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="1e6fa-178">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-178">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="1e6fa-179">Перейдите на вкладку **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-179">Click the **Build** tab.</span></span> <span data-ttu-id="1e6fa-180">Укажите выходной путь, ведущий в то же расположение, которое вы использовали в проекте TypeEquivalenceInterface, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-180">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="1e6fa-181">Не закрывая окно редактирования свойств проекта, откройте вкладку **Подписывание**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-181">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="1e6fa-182">Выберите параметр **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-182">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="1e6fa-183">В списке **Выберите файл ключа строгого имени** выберите **<Создать...>**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-183">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="1e6fa-184">В поле **Имя файла ключа** введите `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-184">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="1e6fa-185">Снимите флажок **Защитить файл ключа паролем**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-185">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="1e6fa-186">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-186">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1e6fa-187">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-187">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="1e6fa-188">Откройте вкладку **Обзор** и перейдите в папку выходного пути.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-188">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="1e6fa-189">Выберите файл TypeEquivalenceInterface.dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-189">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="1e6fa-190">В **обозревателе решений** разверните папку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-190">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="1e6fa-191">Выберите ссылку TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-191">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="1e6fa-192">В окне свойств для ссылки TypeEquivalenceInterface присвойте свойству **Указанная версия** значение **False**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-192">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="1e6fa-193">Добавьте следующий код в файл класса SampleClass, чтобы создать класс SampleClass.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-193">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. <span data-ttu-id="1e6fa-194">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-194">Save the project.</span></span>  
  
10. <span data-ttu-id="1e6fa-195">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-195">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="1e6fa-196">DLL-файл библиотеки классов компилируется и сохраняется по указанному выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-196">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="1e6fa-197">Создание проекта клиента</span><span class="sxs-lookup"><span data-stu-id="1e6fa-197">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="1e6fa-198">Создание проекта клиента для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="1e6fa-198">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="1e6fa-199">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-199">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="1e6fa-200">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-200">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="1e6fa-201">В области **Шаблоны** выберите пункт **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-201">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="1e6fa-202">В поле **Имя** введите `TypeEquivalenceClient` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-202">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="1e6fa-203">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-203">The new project is created.</span></span>  
  
3.  <span data-ttu-id="1e6fa-204">Щелкните проект TypeEquivalenceClient правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-204">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="1e6fa-205">Перейдите на вкладку **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-205">Click the **Build** tab.</span></span> <span data-ttu-id="1e6fa-206">Укажите выходной путь, ведущий в то же расположение, которое вы использовали в проекте TypeEquivalenceInterface, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-206">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="1e6fa-207">Щелкните проект TypeEquivalenceClient правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-207">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="1e6fa-208">Откройте вкладку **Обзор** и перейдите в папку выходного пути.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-208">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="1e6fa-209">Выберите файл TypeEquivalenceInterface.dll (не TypeEquivalenceRuntime.dll) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-209">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="1e6fa-210">В **обозревателе решений** разверните папку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-210">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="1e6fa-211">Выберите ссылку TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-211">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="1e6fa-212">В окне свойств для ссылки TypeEquivalenceInterface присвойте свойству **Внедрить типы взаимодействия** значение **True**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-212">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="1e6fa-213">Добавьте в файл Program.cs следующий код, чтобы создать клиентскую программу.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-213">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="1e6fa-214">Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить программу.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-214">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="1e6fa-215">Изменение интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6fa-215">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="1e6fa-216">Изменение интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6fa-216">To modify the interface</span></span>  
  
1.  <span data-ttu-id="1e6fa-217">В Visual Studio откройте меню **Файл**, наведите указатель мыши на пункт **Создать** и щелкните **Проект/решение**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-217">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="1e6fa-218">В диалоговом окне **Открыть проект** щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-218">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="1e6fa-219">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="1e6fa-219">Click the **Application** tab.</span></span> <span data-ttu-id="1e6fa-220">Нажмите кнопку **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-220">Click the **Assembly Information** button.</span></span> <span data-ttu-id="1e6fa-221">Измените значения параметров **Версия сборки** и **Версия файла** на `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-221">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="1e6fa-222">Откройте файл SampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-222">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="1e6fa-223">Добавьте в интерфейс ISampleInterface следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-223">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="1e6fa-224">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-224">Save the file.</span></span>  
  
4.  <span data-ttu-id="1e6fa-225">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-225">Save the project.</span></span>  
  
5.  <span data-ttu-id="1e6fa-226">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-226">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="1e6fa-227">Новая версия DLL-файла библиотеки классов компилируется и сохраняется по указанному выходному пути (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-227">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="1e6fa-228">Изменение класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1e6fa-228">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="1e6fa-229">Изменение класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1e6fa-229">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="1e6fa-230">В Visual Studio откройте меню **Файл**, наведите указатель мыши на пункт **Создать** и щелкните **Проект/решение**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-230">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="1e6fa-231">В диалоговом окне **Открыть проект** щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-231">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="1e6fa-232">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="1e6fa-232">Click the **Application** tab.</span></span> <span data-ttu-id="1e6fa-233">Нажмите кнопку **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-233">Click the **Assembly Information** button.</span></span> <span data-ttu-id="1e6fa-234">Измените значения параметров **Версия сборки** и **Версия файла** на `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-234">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="1e6fa-235">Откройте файл SampleClass.cs.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-235">Open the SampleClass.cs file.</span></span> <span data-ttu-id="1e6fa-236">Добавьте в класс SampleClass следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-236">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="1e6fa-237">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-237">Save the file.</span></span>  
  
4.  <span data-ttu-id="1e6fa-238">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-238">Save the project.</span></span>  
  
5.  <span data-ttu-id="1e6fa-239">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-239">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="1e6fa-240">Обновленная версия DLL-файла библиотеки классов компилируется и сохраняется по указанному ранее выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-240">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="1e6fa-241">В проводнике откройте папку выходного пути (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="1e6fa-241">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="1e6fa-242">Дважды щелкните файл TypeEquivalenceClient.exe, чтобы выполнить программу.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-242">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="1e6fa-243">Новая версия сборки TypeEquivalenceRuntime отображается в программе без повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="1e6fa-243">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6fa-244">См. также</span><span class="sxs-lookup"><span data-stu-id="1e6fa-244">See Also</span></span>  
 <span data-ttu-id="1e6fa-245">[-link (Параметры компилятора C#)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="1e6fa-245">[/link (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span></span>  
 <span data-ttu-id="1e6fa-246">[Руководство по программированию на C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1e6fa-246">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1e6fa-247">[Программирование с использованием сборок](../../../../framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="1e6fa-247">[Programming with Assemblies](../../../../framework/app-domains/programming-with-assemblies.md) </span></span>  
 [<span data-ttu-id="1e6fa-248">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="1e6fa-248">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

