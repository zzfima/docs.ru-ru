---
title: 'Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 1f6176746b783d020c809fb0b5d55d741ce0148b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="88b97-102">Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88b97-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="88b97-103">Внедряя сведения о типе из управляемой сборки со строгим именем, можно свободно объединять типы в приложении, делая версию независимой.</span><span class="sxs-lookup"><span data-stu-id="88b97-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="88b97-104">Это означает, что в программе можно использовать типы из нескольких версий управляемой библиотеки, т. е. необходимость компилировать каждую версию отдельно отпадает.</span><span class="sxs-lookup"><span data-stu-id="88b97-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="88b97-105">Внедрение типов часто используется с COM-взаимодействием, например в приложениях, использующих объекты автоматизации из Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="88b97-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="88b97-106">Сведения о типе внедрения позволяют одной и той же сборке программы работать с различными версиями Microsoft Office на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="88b97-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="88b97-107">Тем не менее внедрение типа можно также использовать с полностью управляемым решением.</span><span class="sxs-lookup"><span data-stu-id="88b97-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="88b97-108">Сведения о типе можно внедрить из сборки, имеющей следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="88b97-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="88b97-109">Сборка предоставляет по крайней мере один открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="88b97-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="88b97-110">Внедренные интерфейсы снабжаются аннотацией с указанием атрибута `ComImport` и атрибута `Guid` (уникальный GUID).</span><span class="sxs-lookup"><span data-stu-id="88b97-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="88b97-111">Сборка снабжается аннотацией с указанием атрибута `ImportedFromTypeLib` или атрибута `PrimaryInteropAssembly`, а также атрибута сборки `Guid`.</span><span class="sxs-lookup"><span data-stu-id="88b97-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="88b97-112">(По умолчанию шаблоны проектов Visual Basic содержат уровня сборки `Guid` атрибута.)</span><span class="sxs-lookup"><span data-stu-id="88b97-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="88b97-113">После того как открытые интерфейсы, доступные для внедрения, будут указаны, можно создать реализующие их классы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="88b97-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="88b97-114">Во время разработки клиентская программа встраивает сведения о типе для этих интерфейсов, ссылаясь на сборку, содержащую открытые интерфейсы и присваивая свойству `Embed Interop Types` ссылки значение `True`.</span><span class="sxs-lookup"><span data-stu-id="88b97-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="88b97-115">Это эквивалентно использованию компилятора командной строки и ссылки на сборку с помощью параметра компилятора `/link`.</span><span class="sxs-lookup"><span data-stu-id="88b97-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="88b97-116">После этого клиентская программа может загружать экземпляры объектов среды выполнения, типизированные как указанные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="88b97-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="88b97-117">При создании новой версии сборки среды выполнения со строгим именем повторная компиляция клиентской программы с обновленной сборкой среды выполнения не требуется.</span><span class="sxs-lookup"><span data-stu-id="88b97-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="88b97-118">Клиентская программа продолжает работать с той версией сборки среды выполнения, которая ей доступна, используя сведения о внедренном типе для открытых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="88b97-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="88b97-119">Поскольку основной функцией внедрения типа является поддержка внедрения сведений о типе из сборок COM-взаимодействия, при внедрении сведений о типе в полностью управляемое решение применяются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="88b97-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="88b97-120">Внедряются только атрибуты, характерные для COM-взаимодействия; другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="88b97-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="88b97-121">Если тип включает универсальные параметры внедренного типа, использовать этот тип как границу сборки нельзя.</span><span class="sxs-lookup"><span data-stu-id="88b97-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="88b97-122">Граница сборки пересекается, например, при вызове метода из другой сборки или выведении типа из типа, определенного в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="88b97-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="88b97-123">Константы не внедряются.</span><span class="sxs-lookup"><span data-stu-id="88b97-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="88b97-124">Класс <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> не поддерживает использование внедренного типа в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="88b97-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="88b97-125">Для поддержки внедренного типа в качестве ключа можно реализовать свой собственный тип словаря.</span><span class="sxs-lookup"><span data-stu-id="88b97-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="88b97-126">В этом пошаговом руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="88b97-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="88b97-127">Создайте сборку со строгим именем и открытым интерфейсом, содержащим сведения о типе, который может быть внедрен.</span><span class="sxs-lookup"><span data-stu-id="88b97-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="88b97-128">Создайте сборку среды выполнения со строгим именем, реализующую открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="88b97-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="88b97-129">Создайте клиентскую программу, внедряющую сведения о типе из открытого интерфейса и создающую экземпляр класса из сборки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="88b97-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="88b97-130">Внесите изменения и создайте сборку среды выполнения заново.</span><span class="sxs-lookup"><span data-stu-id="88b97-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="88b97-131">Запустите клиентскую программу, чтобы увидеть, что новая версия сборки среды выполнения позволяет обойтись без повторной компиляции клиентской программы.</span><span class="sxs-lookup"><span data-stu-id="88b97-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="88b97-132">Создание интерфейса</span><span class="sxs-lookup"><span data-stu-id="88b97-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="88b97-133">Создание проекта интерфейса для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="88b97-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="88b97-134">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="88b97-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="88b97-135">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="88b97-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="88b97-136">Выберите **Библиотеки классов** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="88b97-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="88b97-137">В поле **Имя** введите `TypeEquivalenceInterface` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="88b97-138">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="88b97-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="88b97-139">В **обозревателе решений**, щелкните правой кнопкой мыши файл Class1.vb и нажмите кнопку **переименование**.</span><span class="sxs-lookup"><span data-stu-id="88b97-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="88b97-140">Измените имя файла на `ISampleInterface.vb` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="88b97-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="88b97-141">При переименовании файла класс также будет переименован в `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="88b97-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="88b97-142">Этот класс будет представлять открытый интерфейс для класса.</span><span class="sxs-lookup"><span data-stu-id="88b97-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="88b97-143">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88b97-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="88b97-144">Откройте вкладку **Компиляция**. Укажите выходной путь к местоположению, существующему на компьютере разработчика, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="88b97-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="88b97-145">Это расположение также пригодится при последующей работе с данным пошаговым руководством.</span><span class="sxs-lookup"><span data-stu-id="88b97-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="88b97-146">Не закрывая окно редактирования свойств проекта, откройте вкладку **Подписывание**. Выберите параметр **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="88b97-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="88b97-147">В списке **Выберите файл ключа строгого имени** выберите **<Создать...>**.</span><span class="sxs-lookup"><span data-stu-id="88b97-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="88b97-148">В поле **Имя файла ключа** введите `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="88b97-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="88b97-149">Снимите флажок **Защитить файл ключа паролем**.</span><span class="sxs-lookup"><span data-stu-id="88b97-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="88b97-150">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="88b97-151">Откройте файл ISampleInterface.vb.</span><span class="sxs-lookup"><span data-stu-id="88b97-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="88b97-152">Добавьте следующий код в файл класса ISampleInterface, чтобы создать интерфейс ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="88b97-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```vb  
    Imports System.Runtime.InteropServices  
  
    <ComImport()>  
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>  
    Public Interface ISampleInterface  
        Sub GetUserInput()  
        ReadOnly Property UserInput As String  
    End Interface  
    ```  
  
7.  <span data-ttu-id="88b97-153">В меню **Сервис** выберите пункт **Создать GUID**.</span><span class="sxs-lookup"><span data-stu-id="88b97-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="88b97-154">В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="88b97-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="88b97-155">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="88b97-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="88b97-156">В атрибуте `Guid` удалите пример GUID и вставьте GUID, скопированный из диалогового окна **Создание GUID**.</span><span class="sxs-lookup"><span data-stu-id="88b97-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="88b97-157">Удалите фигурные скобки ({}) из скопированного GUID.</span><span class="sxs-lookup"><span data-stu-id="88b97-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="88b97-158">В меню **Проект** выберите пункт **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="88b97-158">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="88b97-159">В **обозревателе решений**, разверните **Мой проект** папки.</span><span class="sxs-lookup"><span data-stu-id="88b97-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="88b97-160">Дважды щелкните AssemblyInfo.vb.</span><span class="sxs-lookup"><span data-stu-id="88b97-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="88b97-161">Добавьте в файл следующий атрибут.</span><span class="sxs-lookup"><span data-stu-id="88b97-161">Add the following attribute to the file.</span></span>  
  
    ```vb  
    <Assembly: ImportedFromTypeLib("")>  
    ```  
  
     <span data-ttu-id="88b97-162">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="88b97-162">Save the file.</span></span>  
  
11. <span data-ttu-id="88b97-163">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="88b97-163">Save the project.</span></span>  
  
12. <span data-ttu-id="88b97-164">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="88b97-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="88b97-165">DLL-файл библиотеки классов компилируется и сохраняется по указанному выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="88b97-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="88b97-166">Создание класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="88b97-166">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="88b97-167">Создание проекта среды выполнения для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="88b97-167">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="88b97-168">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="88b97-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="88b97-169">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="88b97-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="88b97-170">Выберите **Библиотеки классов** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="88b97-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="88b97-171">В поле **Имя** введите `TypeEquivalenceRuntime` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="88b97-172">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="88b97-172">The new project is created.</span></span>  
  
3.  <span data-ttu-id="88b97-173">В **обозревателе решений**, щелкните правой кнопкой мыши файл Class1.vb и нажмите кнопку **переименование**.</span><span class="sxs-lookup"><span data-stu-id="88b97-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="88b97-174">Измените имя файла на `SampleClass.vb` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="88b97-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="88b97-175">При переименовании файла класс также будет переименован в `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="88b97-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="88b97-176">Этот класс реализует интерфейс `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="88b97-176">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="88b97-177">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88b97-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="88b97-178">Откройте вкладку **Компиляция**. Укажите выходной путь, ведущий в то же расположение, которое вы использовали в проекте TypeEquivalenceInterface, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="88b97-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="88b97-179">Не закрывая окно редактирования свойств проекта, откройте вкладку **Подписывание**. Выберите параметр **Подписать сборку**.</span><span class="sxs-lookup"><span data-stu-id="88b97-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="88b97-180">В списке **Выберите файл ключа строгого имени** выберите **<Создать...>**.</span><span class="sxs-lookup"><span data-stu-id="88b97-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="88b97-181">В поле **Имя файла ключа** введите `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="88b97-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="88b97-182">Снимите флажок **Защитить файл ключа паролем**.</span><span class="sxs-lookup"><span data-stu-id="88b97-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="88b97-183">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-183">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="88b97-184">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="88b97-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="88b97-185">Откройте вкладку **Обзор** и перейдите в папку выходного пути.</span><span class="sxs-lookup"><span data-stu-id="88b97-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="88b97-186">Выберите файл TypeEquivalenceInterface.dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="88b97-187">В меню **Проект** выберите пункт **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="88b97-187">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="88b97-188">В **обозревателе решений** разверните папку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="88b97-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="88b97-189">Выберите ссылку TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="88b97-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="88b97-190">В окне свойств для ссылки TypeEquivalenceInterface присвойте свойству **Указанная версия** значение **False**.</span><span class="sxs-lookup"><span data-stu-id="88b97-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="88b97-191">Добавьте следующий код в файл класса SampleClass, чтобы создать класс SampleClass.</span><span class="sxs-lookup"><span data-stu-id="88b97-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
  
    Public Class SampleClass  
        Implements ISampleInterface  
  
        Private p_UserInput As String  
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput  
            Get  
                Return p_UserInput  
            End Get  
        End Property  
  
        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput  
            Console.WriteLine("Please enter a value:")  
            p_UserInput = Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
10. <span data-ttu-id="88b97-192">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="88b97-192">Save the project.</span></span>  
  
11. <span data-ttu-id="88b97-193">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="88b97-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="88b97-194">DLL-файл библиотеки классов компилируется и сохраняется по указанному выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="88b97-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="88b97-195">Создание проекта клиента</span><span class="sxs-lookup"><span data-stu-id="88b97-195">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="88b97-196">Создание проекта клиента для эквивалентности типа</span><span class="sxs-lookup"><span data-stu-id="88b97-196">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="88b97-197">В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**.</span><span class="sxs-lookup"><span data-stu-id="88b97-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="88b97-198">Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**.</span><span class="sxs-lookup"><span data-stu-id="88b97-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="88b97-199">В области **Шаблоны** выберите пункт **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="88b97-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="88b97-200">В поле **Имя** введите `TypeEquivalenceClient` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="88b97-201">Проект создан.</span><span class="sxs-lookup"><span data-stu-id="88b97-201">The new project is created.</span></span>  
  
3.  <span data-ttu-id="88b97-202">Щелкните проект TypeEquivalenceClient правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88b97-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="88b97-203">Откройте вкладку **Компиляция**. Укажите выходной путь, ведущий в то же расположение, которое вы использовали в проекте TypeEquivalenceInterface, например `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="88b97-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="88b97-204">Щелкните проект TypeEquivalenceClient правой кнопкой мыши и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="88b97-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="88b97-205">Откройте вкладку **Обзор** и перейдите в папку выходного пути.</span><span class="sxs-lookup"><span data-stu-id="88b97-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="88b97-206">Выберите файл TypeEquivalenceInterface.dll (не TypeEquivalenceRuntime.dll) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88b97-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="88b97-207">В меню **Проект** выберите пункт **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="88b97-207">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="88b97-208">В **обозревателе решений** разверните папку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="88b97-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="88b97-209">Выберите ссылку TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="88b97-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="88b97-210">В окне свойств для ссылки TypeEquivalenceInterface присвойте свойству **Внедрить типы взаимодействия** значение **True**.</span><span class="sxs-lookup"><span data-stu-id="88b97-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="88b97-211">Добавьте следующий код в файл Module1.vb, чтобы создать клиентскую программу.</span><span class="sxs-lookup"><span data-stu-id="88b97-211">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
    Imports System.Reflection  
  
    Module Module1  
  
        Sub Main()  
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")  
            Dim sampleClass As ISampleInterface = CType( _  
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)  
            sampleClass.GetUserInput()  
            Console.WriteLine(sampleClass.UserInput)  
            Console.WriteLine(sampleAssembly.GetName().Version)  
            Console.ReadLine()  
        End Sub  
  
    End Module  
    ```  
  
8.  <span data-ttu-id="88b97-212">Нажмите сочетание клавиш CTRL+F5, чтобы собрать и запустить программу.</span><span class="sxs-lookup"><span data-stu-id="88b97-212">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="88b97-213">Изменение интерфейса</span><span class="sxs-lookup"><span data-stu-id="88b97-213">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="88b97-214">Изменение интерфейса</span><span class="sxs-lookup"><span data-stu-id="88b97-214">To modify the interface</span></span>  
  
1.  <span data-ttu-id="88b97-215">В Visual Studio откройте меню **Файл**, наведите указатель мыши на пункт **Создать** и щелкните **Проект/решение**.</span><span class="sxs-lookup"><span data-stu-id="88b97-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="88b97-216">В диалоговом окне **Открыть проект** щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88b97-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="88b97-217">Перейдите на вкладку **Приложение** . Нажмите кнопку **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="88b97-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="88b97-218">Измените значения параметров **Версия сборки** и **Версия файла** на `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="88b97-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="88b97-219">Откройте файл ISampleInterface.vb.</span><span class="sxs-lookup"><span data-stu-id="88b97-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="88b97-220">Добавьте в интерфейс ISampleInterface следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="88b97-220">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```vb  
    Function GetDate() As Date  
    ```  
  
     <span data-ttu-id="88b97-221">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="88b97-221">Save the file.</span></span>  
  
4.  <span data-ttu-id="88b97-222">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="88b97-222">Save the project.</span></span>  
  
5.  <span data-ttu-id="88b97-223">Щелкните проект TypeEquivalenceInterface правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="88b97-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="88b97-224">Новая версия DLL-файла библиотеки классов компилируется и сохраняется по указанному выходному пути (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="88b97-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="88b97-225">Изменение класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="88b97-225">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="88b97-226">Изменение класса среды выполнения</span><span class="sxs-lookup"><span data-stu-id="88b97-226">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="88b97-227">В Visual Studio откройте меню **Файл**, наведите указатель мыши на пункт **Создать** и щелкните **Проект/решение**.</span><span class="sxs-lookup"><span data-stu-id="88b97-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="88b97-228">В диалоговом окне **Открыть проект** щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="88b97-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="88b97-229">Перейдите на вкладку **Приложение** . Нажмите кнопку **Сведения о сборке**.</span><span class="sxs-lookup"><span data-stu-id="88b97-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="88b97-230">Измените значения параметров **Версия сборки** и **Версия файла** на `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="88b97-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="88b97-231">Откройте SampleClass.vbfile.</span><span class="sxs-lookup"><span data-stu-id="88b97-231">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="88b97-232">Добавьте в класс SampleClass следующие строки кода.</span><span class="sxs-lookup"><span data-stu-id="88b97-232">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="88b97-233">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="88b97-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="88b97-234">Щелкните проект TypeEquivalenceRuntime правой кнопкой мыши и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="88b97-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="88b97-235">Обновленная версия DLL-файла библиотеки классов компилируется и сохраняется по указанному ранее выходному пути для сборки (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="88b97-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="88b97-236">В проводнике откройте папку выходного пути (например, C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="88b97-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="88b97-237">Дважды щелкните файл TypeEquivalenceClient.exe, чтобы выполнить программу.</span><span class="sxs-lookup"><span data-stu-id="88b97-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="88b97-238">Новая версия сборки TypeEquivalenceRuntime отображается в программе без повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="88b97-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b97-239">См. также</span><span class="sxs-lookup"><span data-stu-id="88b97-239">See Also</span></span>  
 [<span data-ttu-id="88b97-240">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88b97-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="88b97-241">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="88b97-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="88b97-242">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="88b97-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="88b97-243">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88b97-243">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
