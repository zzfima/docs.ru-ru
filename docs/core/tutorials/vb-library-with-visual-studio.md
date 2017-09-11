---
title: "Создание библиотеки классов с помощью Visual Basic и .NET Core в Visual Studio 2017"
description: "Сведения о сборке библиотеки классов, написанной на языке Visual Basic, с помощью Visual Studio 2017"
keywords: ".NET Core, библиотека классов .NET Standard, Visual Studio 2017, Visual Basic"
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
ms.devlang: vb
ms.translationtype: HT
ms.sourcegitcommit: 3a25c1c3b540bac8ef963a8bbf708b0700c3e9e2
ms.openlocfilehash: a933e1eef6e4e9814aeba4206469a64563a7e91d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/12/2017

---

# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a><span data-ttu-id="ad168-104">Создание библиотеки классов с помощью Visual Basic и .NET Core в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ad168-104">Building a class library with Visual Basic and .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="ad168-105">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="ad168-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="ad168-106">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ad168-106">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="ad168-107">Когда вы завершите создание библиотеки классов, вы сможете по своему усмотрению распространять ее как независимый компонент или включить в состав одного или нескольких приложений.</span><span class="sxs-lookup"><span data-stu-id="ad168-107">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="ad168-108">Список версий .NET Standard и поддерживаемых ими платформ см. в разделе [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="ad168-108">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="ad168-109">В этой статье вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="ad168-109">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="ad168-110">Вы реализуете его как [метод расширения](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ad168-110">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="ad168-111">Создание решения для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="ad168-111">Creating a class library solution</span></span>

<span data-ttu-id="ad168-112">Начнем с создания решения для нашего проекта библиотеки классов и связанных с ней проектов.</span><span class="sxs-lookup"><span data-stu-id="ad168-112">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="ad168-113">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="ad168-113">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="ad168-114">Чтобы создать решение, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="ad168-114">To create the solution:</span></span>

1. <span data-ttu-id="ad168-115">В строке меню Visual Studio выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="ad168-115">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="ad168-116">В диалоговом окне **Новый проект** разверните узел **Другие типы проектов** и выберите **Решения Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ad168-116">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="ad168-117">Присвойте решению имя ClassLibraryProjects и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad168-117">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Диалоговое окно создания проекта](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="ad168-119">Создание проекта для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="ad168-119">Creating the class library project</span></span>

<span data-ttu-id="ad168-120">Теперь можно создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="ad168-120">Create your class library project:</span></span>

1. <span data-ttu-id="ad168-121">В **обозревателе решений** щелкните правой кнопкой мыши решение **ClassLibraryProjects** и в контекстном меню выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="ad168-121">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="ad168-122">В диалоговом окне **Добавление нового проекта** разверните узел **Visual Basic**, выберите узел **.NET Standard**, а затем — шаблон проекта **Библиотека классов (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="ad168-122">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="ad168-123">В текстовом поле **Имя** введите имя проекта StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="ad168-123">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="ad168-124">Нажмите **ОК**, чтобы создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="ad168-124">Select **OK** to create the class library project.</span></span>

   ![Диалоговое окно "Добавление нового проекта"](./media/vb-library-with-visual-studio/libproject.png)

   <span data-ttu-id="ad168-126">Окно кода затем откроется в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ad168-126">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Окно приложения Visual Studio, отображающее код шаблона библиотеки классов по умолчанию](./media/vb-library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="ad168-128">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ad168-128">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="ad168-129">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ad168-129">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="ad168-130">В текстовом поле **Целевая платформа** указано, что целевой платформой является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="ad168-130">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="ad168-132">Кроме того, в диалоговом окне **Свойства** удалите текст в поле **Корневое пространство имен**.</span><span class="sxs-lookup"><span data-stu-id="ad168-132">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="ad168-133">Для каждого проекта Visual Basic автоматически создает пространство имен, соответствующее имени проекта. Все пространства имен, определяемые в файлах с исходным кодом, являются родительскими по отношению к этому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="ad168-133">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="ad168-134">Нам необходимо определить пространство имен верхнего уровня с помощью ключевого слова [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad168-134">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="ad168-135">Замените код, отображаемый в окне кода, следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="ad168-135">Replace the code in the code window with the following code and save the file:</span></span>

  <span data-ttu-id="ad168-136">[!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad168-136">[!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]</span></span>

   <span data-ttu-id="ad168-137">Библиотека классов (`UtilityLibraries.StringLibrary`) содержит метод с именем `StartsWithUpper`, который возвращает значение <xref:System.Boolean>. Это значение указывает, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="ad168-137">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="ad168-138">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="ad168-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="ad168-139">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=fullName> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="ad168-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=fullName> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="ad168-140">В строке меню выберите **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="ad168-140">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="ad168-141">Проект должен скомпилироваться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="ad168-141">The project should compile without error.</span></span>

   ![Область вывода, показывающая успешное завершение сборки](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a><span data-ttu-id="ad168-143">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ad168-143">Next step</span></span>

<span data-ttu-id="ad168-144">Итак, вы успешно создали библиотеку.</span><span class="sxs-lookup"><span data-stu-id="ad168-144">You've successfully built the library.</span></span> <span data-ttu-id="ad168-145">Пока вы еще не вызывали ее методов, поэтому нельзя быть уверенным, что все работает так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="ad168-145">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="ad168-146">Следующий шаг в разработке библиотеки — тестирование с помощью [проекта модульного теста](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ad168-146">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>

