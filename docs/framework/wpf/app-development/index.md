---
title: Разработка приложений
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: b0bdf49e0bb3d9bfa3fc4e7fd94aa68ee4ea0bb3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636397"
---
# <a name="application-development"></a><span data-ttu-id="8dfbe-102">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="8dfbe-102">Application Development</span></span>
<a name="introduction"></a><span data-ttu-id="8dfbe-103">Windows Presentation Foundation (WPF) — это структура представления, которую можно использовать для разработки приложений следующих типов:</span><span class="sxs-lookup"><span data-stu-id="8dfbe-103">Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
- <span data-ttu-id="8dfbe-104">Автономные приложения (традиционные приложения Windows, созданные как исполняемые сборки, которые устанавливаются и запускаются с клиентского компьютера).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-104">Standalone Applications (traditional style Windows applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
- <span data-ttu-id="8dfbe-105">Приложения браузера XAML (XBAP) (приложения, состоящие из страниц навигации, построенных как исполняемые сборки и размещенные в веб-браузерах, таких как Microsoft Internet Explorer или Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-105">XAML browser applications (XBAPs) (applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as Microsoft Internet Explorer or Mozilla Firefox).</span></span>  
  
- <span data-ttu-id="8dfbe-106">пользовательские библиотеки элементов управления (неисполняемые сборки, содержащие многократно используемые элементы управления);</span><span class="sxs-lookup"><span data-stu-id="8dfbe-106">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
- <span data-ttu-id="8dfbe-107">библиотеки классов (неисполняемые сборки, содержащие многократно используемые классы).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-107">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8dfbe-108">Использование типов WPF в службе Windows настоятельно не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="8dfbe-109">При попытке использовать эти возможности в службе Windows они могут не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-109">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="8dfbe-110">Для создания этого набора приложений в WPF реализован узел служб.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-110">To build this set of applications, WPF implements a host of services.</span></span> <span data-ttu-id="8dfbe-111">Этот раздел предоставляет обзор этих служб и место, где искать дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-111">This topic provides an overview of these services and where to find more information.</span></span>  

<a name="Application_Management"></a>   
## <a name="application-management"></a><span data-ttu-id="8dfbe-112">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="8dfbe-112">Application Management</span></span>  
 <span data-ttu-id="8dfbe-113">Для исполняемых приложений WPF обычно требуется основной набор функций, включающий следующее:</span><span class="sxs-lookup"><span data-stu-id="8dfbe-113">Executable WPF applications commonly require a core set of functionality that includes the following:</span></span>  
  
- <span data-ttu-id="8dfbe-114">создание и управление общей инфраструктурой приложений (включая создание метода точки входа и цикл обработки сообщений Windows для получения системных и входящих сообщений);</span><span class="sxs-lookup"><span data-stu-id="8dfbe-114">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
- <span data-ttu-id="8dfbe-115">отслеживание и взаимодействие со временем существования приложения;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-115">Tracking and interacting with the lifetime of an application.</span></span>  
  
- <span data-ttu-id="8dfbe-116">извлечение и обработка параметров командной строки;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-116">Retrieving and processing command-line parameters.</span></span>  
  
- <span data-ttu-id="8dfbe-117">совместное использование свойств области приложения и ресурсов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)];</span><span class="sxs-lookup"><span data-stu-id="8dfbe-117">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
- <span data-ttu-id="8dfbe-118">обнаружение и обработка необработанных исключений;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-118">Detecting and processing unhandled exceptions.</span></span>  
  
- <span data-ttu-id="8dfbe-119">возврат кодов завершения;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-119">Returning exit codes.</span></span>  
  
- <span data-ttu-id="8dfbe-120">управление окнами в автономных приложениях;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-120">Managing windows in standalone applications.</span></span>  
  
- <span data-ttu-id="8dfbe-121">Отслеживание переходов в приложениях браузера XAML (XBAP) и автономных приложениях с окнами навигации и фреймами.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-121">Tracking navigation in XAML browser applications (XBAPs), and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="8dfbe-122">Эти возможности реализуются с помощью класса <xref:System.Windows.Application>, который добавляется в приложения с помощью *определения приложения*.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-122">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="8dfbe-123">Дополнительные сведения см. в разделе [Общие сведения об управлении приложением](application-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-123">For more information, see [Application Management Overview](application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="8dfbe-124">Ресурсы, Содержимое и Файлы данных WPF-приложения</span><span class="sxs-lookup"><span data-stu-id="8dfbe-124">WPF Application Resource, Content, and Data Files</span></span>  
 <span data-ttu-id="8dfbe-125">WPF расширяет базовую поддержку в Microsoft .NET Framework для внедренных ресурсов с поддержкой трех типов неисполняемых файлов данных: ресурсов, содержимого и данных.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-125">WPF extends the core support in the Microsoft .NET Framework for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="8dfbe-126">Дополнительные сведения см. в разделе [Файлы ресурсов, содержимого и данных WPF-приложения](wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-126">For more information, see [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="8dfbe-127">Ключевым компонентом поддержки неисполняемых файлов данных WPF является возможность определять и загружать их с помощью уникального универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-127">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique URI.</span></span> <span data-ttu-id="8dfbe-128">Дополнительные сведения см. в разделе [URI типа "pack" в WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-128">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="8dfbe-129">Окна и диалоговые окна</span><span class="sxs-lookup"><span data-stu-id="8dfbe-129">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="8dfbe-130">Пользователи взаимодействуют с автономными приложениями WPF через Windows.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-130">Users interact with WPF standalone applications through windows.</span></span> <span data-ttu-id="8dfbe-131">Предназначением окна является размещение содержимого приложения и предоставление функциональных возможностей приложения, которые обычно позволяют пользователям взаимодействовать с содержимым.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-131">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="8dfbe-132">В WPF эти окна инкапсулированы классом <xref:System.Windows.Window>, который поддерживает:</span><span class="sxs-lookup"><span data-stu-id="8dfbe-132">In WPF, windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
- <span data-ttu-id="8dfbe-133">создание и отображение окон;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-133">Creating and showing windows.</span></span>  
  
- <span data-ttu-id="8dfbe-134">установка отношений владельца/собственного окна;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-134">Establishing owner/owned window relationships.</span></span>  
  
- <span data-ttu-id="8dfbe-135">настройка внешнего вида окна (например, размер, расположение, значки, текст заголовка, границы);</span><span class="sxs-lookup"><span data-stu-id="8dfbe-135">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
- <span data-ttu-id="8dfbe-136">отслеживание и взаимодействие со временем существования окна.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-136">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="8dfbe-137">Дополнительные сведения см. в разделе [Общие сведения об окнах WPF](wpf-windows-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-137">For more information, see [WPF Windows Overview](wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="8dfbe-138"><xref:System.Windows.Window> поддерживает возможность создать особый тип окна, известный как диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-138"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="8dfbe-139">Можно создавать модальные и немодальные типы диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-139">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="8dfbe-140">Для удобства и преимуществ повторного использования и согласованного взаимодействия с пользователем в приложениях WPF предоставляет три общих диалоговых окна Windows: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>и <xref:System.Windows.Controls.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-140">For convenience, and the benefits of reusability and a consistent user experience across applications, WPF exposes three of the common Windows dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="8dfbe-141">Окно сообщения представляет собой особый тип диалогового окна для отображения важной текстовой информации для пользователей и задания простых вопросов (да, нет, ОК, отмена).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-141">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="8dfbe-142">Класс <xref:System.Windows.MessageBox> используется для создания и отображения окон сообщений.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-142">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="8dfbe-143">Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](dialog-boxes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-143">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>   
## <a name="navigation"></a><span data-ttu-id="8dfbe-144">Навигация в</span><span class="sxs-lookup"><span data-stu-id="8dfbe-144">Navigation</span></span>  
 <span data-ttu-id="8dfbe-145">WPF поддерживает навигацию в стиле веб-страниц, используя страницы (<xref:System.Windows.Controls.Page>) и гиперссылки (<xref:System.Windows.Documents.Hyperlink>).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-145">WPF supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="8dfbe-146">Навигация может быть реализована разнообразными способами, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="8dfbe-146">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
- <span data-ttu-id="8dfbe-147">автономные страницы, размещенные в веб-браузере;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-147">Standalone pages that are hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="8dfbe-148">Страницы, скомпилированные в XBAP, размещенные в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-148">Pages compiled into an XBAP that is hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="8dfbe-149">страницы, скомпилированные в автономном приложении и размещенные в окне навигации (<xref:System.Windows.Navigation.NavigationWindow>);</span><span class="sxs-lookup"><span data-stu-id="8dfbe-149">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
- <span data-ttu-id="8dfbe-150">Страницы, размещенные на кадре (<xref:System.Windows.Controls.Frame>), которые могут размещаться на автономной странице, или на странице, скомпилированной в XBAP или в автономное приложение.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-150">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an XBAP or a standalone application.</span></span>  
  
 <span data-ttu-id="8dfbe-151">Для упрощения навигации в WPF реализованы следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="8dfbe-151">To facilitate navigation, WPF implements the following:</span></span>  
  
- <span data-ttu-id="8dfbe-152"><xref:System.Windows.Navigation.NavigationService>, общий механизм навигации для обработки запросов навигации, используемый <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>и XBAP для поддержки навигации внутри приложения.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-152"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and XBAPs to support intra-application navigation.</span></span>  
  
- <span data-ttu-id="8dfbe-153">методы навигации для инициирования навигации;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-153">Navigation methods to initiate navigation.</span></span>  
  
- <span data-ttu-id="8dfbe-154">события переходов для отслеживания и взаимодействия со временем существования перехода;</span><span class="sxs-lookup"><span data-stu-id="8dfbe-154">Navigation events to track and interact with navigation lifetime.</span></span>  
  
- <span data-ttu-id="8dfbe-155">запоминание переходов назад и вперед с использованием журнала, который может быть проверен и обработан.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-155">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="8dfbe-156">Сведения см. в разделе [Общие сведения о переходах](navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-156">For information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 <span data-ttu-id="8dfbe-157">WPF также поддерживает Специальный тип навигации, известный как структурированная навигация.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-157">WPF also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="8dfbe-158">Структурированная навигация может использоваться для вызова одной или нескольких страниц, которые возвращают данные структурированным и предсказуемым способом, согласованным с вызывающими функциями.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-158">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="8dfbe-159">Эта возможность зависит от класса <xref:System.Windows.Navigation.PageFunction%601>, который описан далее в разделе [Общие сведения о структурной навигации](structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-159">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](structured-navigation-overview.md).</span></span> <span data-ttu-id="8dfbe-160"><xref:System.Windows.Navigation.PageFunction%601> также позволяет упростить создание сложных топологий переходов, которые описаны в разделе [Общие сведения о топологии переходов](navigation-topologies-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-160"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>   
## <a name="hosting"></a><span data-ttu-id="8dfbe-161">Размещение</span><span class="sxs-lookup"><span data-stu-id="8dfbe-161">Hosting</span></span>  
 <span data-ttu-id="8dfbe-162">XBAP можно размещать в Microsoft Internet Explorer или Firefox.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-162">XBAPs can be hosted in Microsoft Internet Explorer or Firefox.</span></span> <span data-ttu-id="8dfbe-163">Каждая модель размещения имеет свой собственный набор разрешений и ограничений, которые рассматриваются в разделе [Размещение](hosting-wpf-applications.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-163">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a><span data-ttu-id="8dfbe-164">Построение и развертывание</span><span class="sxs-lookup"><span data-stu-id="8dfbe-164">Build and Deploy</span></span>  
 <span data-ttu-id="8dfbe-165">Несмотря на то, что простые приложения WPF можно создавать из командной строки с помощью компиляторов с командной строкой, WPF интегрируется с Visual Studio для предоставления дополнительной поддержки, которая упрощает процесс разработки и сборки.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-165">Although simple WPF applications can be built from a command prompt using command-line compilers, WPF integrates with Visual Studio to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="8dfbe-166">Дополнительные сведения см. в разделе [Построение приложения WPF](building-a-wpf-application-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-166">For more information, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="8dfbe-167">В зависимости от типа приложения вы можете выбрать один или несколько параметров развертывания.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-167">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="8dfbe-168">Дополнительные сведения см. в разделе [Развертывание приложений WPF](deploying-a-wpf-application-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-168">For more information, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="8dfbe-169">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8dfbe-169">Related Topics</span></span>  
  
|<span data-ttu-id="8dfbe-170">Заголовок</span><span class="sxs-lookup"><span data-stu-id="8dfbe-170">Title</span></span>|<span data-ttu-id="8dfbe-171">Описание</span><span class="sxs-lookup"><span data-stu-id="8dfbe-171">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8dfbe-172">Общие сведения об управлении приложением</span><span class="sxs-lookup"><span data-stu-id="8dfbe-172">Application Management Overview</span></span>](application-management-overview.md)|<span data-ttu-id="8dfbe-173">Общие сведения о классе <xref:System.Windows.Application>, включая управление временем существования приложения, окнами, ресурсами приложений и навигацией.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-173">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="8dfbe-174">Windows в WPF</span><span class="sxs-lookup"><span data-stu-id="8dfbe-174">Windows in WPF</span></span>](windows-in-wpf-applications.md)|<span data-ttu-id="8dfbe-175">Сведения об управлении окнами в приложении, включая способы использования класса <xref:System.Windows.Window> и диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-175">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="8dfbe-176">Общие сведения о переходах</span><span class="sxs-lookup"><span data-stu-id="8dfbe-176">Navigation Overview</span></span>](navigation-overview.md)|<span data-ttu-id="8dfbe-177">Общие сведения об управлении навигацией по страницам приложения.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-177">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="8dfbe-178">Размещение</span><span class="sxs-lookup"><span data-stu-id="8dfbe-178">Hosting</span></span>](hosting-wpf-applications.md)|<span data-ttu-id="8dfbe-179">Содержит общие сведения о приложениях браузера XAML (XBAP).</span><span class="sxs-lookup"><span data-stu-id="8dfbe-179">Provides an overview of XAML browser applications (XBAPs).</span></span>|  
|[<span data-ttu-id="8dfbe-180">Сборка и развертывание</span><span class="sxs-lookup"><span data-stu-id="8dfbe-180">Build and Deploy</span></span>](building-and-deploying-wpf-applications.md)|<span data-ttu-id="8dfbe-181">Описание процесса сборки и развертывания приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-181">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="8dfbe-182">Введение в WPF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8dfbe-182">Introduction to WPF in Visual Studio</span></span>](../getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="8dfbe-183">Описание основных возможностей WPF.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-183">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="8dfbe-184">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="8dfbe-184">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="8dfbe-185">Пошаговое руководство, в котором демонстрируется создание приложения WPF с использованием навигации по страницам, макета, элементов управления, изображений, стилей и привязок.</span><span class="sxs-lookup"><span data-stu-id="8dfbe-185">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
