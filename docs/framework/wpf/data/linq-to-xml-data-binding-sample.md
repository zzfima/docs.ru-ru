---
title: Пример привязки данных LINQ to XML
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921224"
---
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="c1af5-102">Пример привязки данных LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c1af5-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="c1af5-103">В этой статье описывается пример LinqToXmlDataBinding — приложение Windows Presentation Foundation (WPF), которое привязывает компоненты пользовательского интерфейса к внедренному источнику XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c1af5-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="c1af5-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="c1af5-104">Overview</span></span>

<span data-ttu-id="c1af5-105">Пример LinqToXmlDataBinding — это приложение Windows Presentation Foundation (WPF), которое содержит C# исходные файлы XAML и.</span><span class="sxs-lookup"><span data-stu-id="c1af5-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="c1af5-106">Внедренный XML-документ определяет список книг.</span><span class="sxs-lookup"><span data-stu-id="c1af5-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="c1af5-107">Приложение позволяет пользователю просматривать, добавлять, удалять и изменять записи книги.</span><span class="sxs-lookup"><span data-stu-id="c1af5-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="c1af5-108">Существует два основных исходных файла:</span><span class="sxs-lookup"><span data-stu-id="c1af5-108">There are two primary source files:</span></span>

- <span data-ttu-id="c1af5-109">Файл [L2DBForm.xaml](l2dbform-xaml-source-code.md) содержит декларацию кода XAML для пользовательского интерфейса главного окна.</span><span class="sxs-lookup"><span data-stu-id="c1af5-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="c1af5-110">Он также содержит раздел ресурсов окна, который определяет поставщика данных и внедренный XML-документ для списков книг.</span><span class="sxs-lookup"><span data-stu-id="c1af5-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="c1af5-111">Файл [L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) содержит методы инициализации и обработки событий, связанные с этим пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="c1af5-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="c1af5-112">Главное окно разделено по вертикали на четыре интерфейсных раздела.</span><span class="sxs-lookup"><span data-stu-id="c1af5-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="c1af5-113">Раздел **XML** отображает необработанный код внедренного листинга книг на языке XML.</span><span class="sxs-lookup"><span data-stu-id="c1af5-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="c1af5-114">Раздел **Список книг** отображает выполненные в формате стандартного текста записи книг и дает пользователю возможность выбирать и удалять отдельные записи.</span><span class="sxs-lookup"><span data-stu-id="c1af5-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="c1af5-115">Раздел **Правка выделенной книги** позволяет пользователю изменять значения, связанные с книжной записью, выделенной в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c1af5-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="c1af5-116">Раздел **Добавить новую книгу** позволяет создавать новую запись в книге на базе значений, введенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="c1af5-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="c1af5-117">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="c1af5-117">Run the sample</span></span>

<span data-ttu-id="c1af5-118">В этом разделе показано, как создать и построить проект LinqToXmlDataBinding в Visual Studio и как запустить полученное приложение LinqToXmlDataBinding Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c1af5-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="c1af5-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c1af5-119">Create the project</span></span>

1. <span data-ttu-id="c1af5-120">Запустите Visual Studio и создайте **приложение WPF** на C# с именем **LinqToXmlDataBinding**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="c1af5-121">В проекте необходимо использовать .NET Framework 3.5 (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="c1af5-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="c1af5-122">Добавьте в проект ссылки для следующих сборок .NET, если они еще не заданы:</span><span class="sxs-lookup"><span data-stu-id="c1af5-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="c1af5-123">System.Data</span><span class="sxs-lookup"><span data-stu-id="c1af5-123">System.Data</span></span>
    - <span data-ttu-id="c1af5-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="c1af5-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="c1af5-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c1af5-125">System.Xml</span></span>
    - <span data-ttu-id="c1af5-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c1af5-126">System.Xml</span></span>

1. <span data-ttu-id="c1af5-127">Выполните сборку решения, нажав **Ctrl**+**Shift**+**B**, а затем запустите его с помощью клавиши **F5**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="c1af5-128">Проект должен быть скомпилирован без ошибок и выполнен как обычное приложение WPF.</span><span class="sxs-lookup"><span data-stu-id="c1af5-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="c1af5-129">Добавить код</span><span class="sxs-lookup"><span data-stu-id="c1af5-129">Add code</span></span>

1. <span data-ttu-id="c1af5-130">В **обозревателе решений** переименуйте исходный файл **Window1.xaml** в **L2XDBForm.xaml**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="c1af5-131">Зависимый исходный файл Window1.xaml.cs автоматически переименовывается в L2XDBForm.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="c1af5-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="c1af5-132">Замените исходный код, обнаруженный в файле **L2XDBForm. XAML** , [исходным кодом L2DBForm. XAML](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="c1af5-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="c1af5-133">Для работы с этим файлом используйте представление источника данных XAML.</span><span class="sxs-lookup"><span data-stu-id="c1af5-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="c1af5-134">Аналогичным образом замените источник в **L2XDBForm.XAML.CS** на [Исходный код L2DBForm.XAML.CS](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="c1af5-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="c1af5-135">В файле **app. XAML**замените все вхождения строки **Window1. XAML** на **L2XDBForm. XAML**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="c1af5-136">Выполните сборку решения, нажав **Ctrl**+**Shift**+**B**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="c1af5-137">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="c1af5-137">Run the app</span></span>

<span data-ttu-id="c1af5-138">Приложение LinqToXmlDataBinding позволяет пользователю просматривать список книг, сохраненных в виде внедренного XML-элемента, и управлять им.</span><span class="sxs-lookup"><span data-stu-id="c1af5-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="c1af5-139">Запустите приложение, нажав клавишу **F5** (начать отладку) или **клавишу CTRL**+**F5** (Запуск без отладки).</span><span class="sxs-lookup"><span data-stu-id="c1af5-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="c1af5-140">Откроется окно программы с заголовком **Привязка данных WPF с помощью LINQ to XML**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="c1af5-141">В верхней части пользовательского интерфейса отображается необработанный **код XML** , представляющий список книг.</span><span class="sxs-lookup"><span data-stu-id="c1af5-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="c1af5-142">Он выводится с помощью элемента управления WPF <xref:System.Windows.Controls.TextBlock>, не включающего взаимодействие с мышью или клавиатурой.</span><span class="sxs-lookup"><span data-stu-id="c1af5-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="c1af5-143">Второй вертикальный раздел, обозначенный как **Список книг**, отображает упорядоченный список книг в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="c1af5-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="c1af5-144">В нем используется элемент управления <xref:System.Windows.Controls.ListBox>, допускающий выбор с помощью мыши или клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c1af5-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="c1af5-145">Добавление и удаление книг</span><span class="sxs-lookup"><span data-stu-id="c1af5-145">Add and delete books</span></span>

<span data-ttu-id="c1af5-146">Чтобы добавить новую книгу в список, введите значения в поле **идентификатор** и **значение** <xref:System.Windows.Controls.TextBox> элементы управления в последнем разделе, **добавьте новую книгу**, а затем выберите **Добавить книгу**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="c1af5-147">Книга добавляется в список в списках «книга» и «XML».</span><span class="sxs-lookup"><span data-stu-id="c1af5-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="c1af5-148">Эта программа не выполняет проверку правильности входных значений.</span><span class="sxs-lookup"><span data-stu-id="c1af5-148">This program does not validate input values.</span></span>

<span data-ttu-id="c1af5-149">Чтобы удалить существующую книгу из списка, выберите ее в разделе **список книг** , а затем выберите **Удалить выбранную книгу**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="c1af5-150">Запись книги удаляется из списков книг и необработанных источников XML.</span><span class="sxs-lookup"><span data-stu-id="c1af5-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="c1af5-151">Изменение записи книги</span><span class="sxs-lookup"><span data-stu-id="c1af5-151">Edit a book entry</span></span>

1. <span data-ttu-id="c1af5-152">Выделите книгу во втором разделе **Список книг**.</span><span class="sxs-lookup"><span data-stu-id="c1af5-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="c1af5-153">Его текущие значения отображаются в разделе **изменение выбранной книги** .</span><span class="sxs-lookup"><span data-stu-id="c1af5-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="c1af5-154">Измените значения с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c1af5-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="c1af5-155">Как только <xref:System.Windows.Controls.TextBox> управления теряет фокус, изменения автоматически распространяются на XML-источники и списки книг.</span><span class="sxs-lookup"><span data-stu-id="c1af5-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
