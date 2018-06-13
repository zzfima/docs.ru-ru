---
title: Пошаговое руководство. Размещение часов WPF в Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 58e4b1dd311ccd6e1bbab79f4c4dda2207f96eaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549702"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="7c60a-102">Пошаговое руководство. Размещение часов WPF в Win32</span><span class="sxs-lookup"><span data-stu-id="7c60a-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="7c60a-103">Для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения, используют <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.</span><span class="sxs-lookup"><span data-stu-id="7c60a-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="7c60a-104">Сначала создайте <xref:System.Windows.Interop.HwndSource>, задав для него параметры аналогично CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="7c60a-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="7c60a-105">Указать <xref:System.Windows.Interop.HwndSource> о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого, которое требуется поместить.</span><span class="sxs-lookup"><span data-stu-id="7c60a-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="7c60a-106">Наконец, получается HWND из <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="7c60a-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="7c60a-107">В этом пошаговом руководстве описывается создание смешанного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложение, заново реализует операционной системы **свойства даты и времени** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7c60a-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7c60a-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7c60a-108">Prerequisites</span></span>  
 <span data-ttu-id="7c60a-109">В разделе [WPF и взаимодействие Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="7c60a-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="7c60a-110">Как использовать этот учебник</span><span class="sxs-lookup"><span data-stu-id="7c60a-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="7c60a-111">Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7c60a-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="7c60a-112">Образец, поддерживаемый учебника [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051), но в этом образце конечного продукта, отражающего свет.</span><span class="sxs-lookup"><span data-stu-id="7c60a-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="7c60a-113">Этот учебник приведены шаги, как если бы вы начали с существующим [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] собственный проект, возможно ранее существующим проектом и добавили размещенных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение.</span><span class="sxs-lookup"><span data-stu-id="7c60a-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="7c60a-114">Вы можете сравнить конечного продукта с [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="7c60a-114">You can compare your end product with [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="7c60a-115">Пошаговое руководство по WPF внутри Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="7c60a-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="7c60a-116">На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:</span><span class="sxs-lookup"><span data-stu-id="7c60a-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="7c60a-117">![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="7c60a-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="7c60a-118">Этот диалог можно создать заново, создав C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]и использование редактора диалоговых окон для создания следующих:</span><span class="sxs-lookup"><span data-stu-id="7c60a-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="7c60a-119">![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="7c60a-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="7c60a-120">(Необходимо использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] использовать <xref:System.Windows.Interop.HwndSource>, и вам не нужно использовать C++ для записи [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программы, но это весьма распространенный способ сделать это и легко решается также поэтапно предоставляется в руководстве).</span><span class="sxs-lookup"><span data-stu-id="7c60a-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="7c60a-121">Необходимо выполнить пять отдельных этапов, чтобы поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов в диалоговом окне:</span><span class="sxs-lookup"><span data-stu-id="7c60a-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="7c60a-122">Включить вашей [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта для вызова управляемого кода (**/CLR**), изменив параметры проекта в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c60a-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="7c60a-123">Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="7c60a-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="7c60a-124">Поместите этот [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> внутри <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="7c60a-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="7c60a-125">Получите HWND для, <xref:System.Windows.Controls.Page> с помощью <xref:System.Windows.Interop.HwndSource.Handle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7c60a-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="7c60a-126">Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , чтобы указать место размещения HWND в большем [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения</span><span class="sxs-lookup"><span data-stu-id="7c60a-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="7c60a-127">/clr</span><span class="sxs-lookup"><span data-stu-id="7c60a-127">/clr</span></span>  
 <span data-ttu-id="7c60a-128">Первым шагом является преобразование этого неуправляемого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проект, в который можно вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="7c60a-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="7c60a-129">Используйте параметр компилятора/CLR, который свяжет необходимые библиотеки DLL и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c60a-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="7c60a-130">Чтобы включить использование управляемого кода в проекте C++: щелкните правой кнопкой мыши на проекте win32clock и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="7c60a-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="7c60a-131">На **Общие** поддержки среды CLR, чтобы изменить страницу свойств (по умолчанию), `/clr`.</span><span class="sxs-lookup"><span data-stu-id="7c60a-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="7c60a-132">Добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll и UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="7c60a-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="7c60a-133">(Следующие инструкции предполагают, что операционная система установлена на диске C:.)</span><span class="sxs-lookup"><span data-stu-id="7c60a-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="7c60a-134">Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** , а внутри этого диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="7c60a-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="7c60a-135">Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="7c60a-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="7c60a-136">Нажмите кнопку **добавить новую ссылку**, щелкните вкладку "Обзор", введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="7c60a-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="7c60a-137">Повторите то же самое для PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="7c60a-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="7c60a-138">Повторите то же самое для WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="7c60a-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="7c60a-139">Повторите то же самое для UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="7c60a-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="7c60a-140">Повторите то же самое для UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="7c60a-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="7c60a-141">Нажмите кнопку **добавить новую ссылку**, выберите System.dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c60a-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="7c60a-142">Нажмите кнопку **ОК** для выхода из страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="7c60a-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="7c60a-143">Наконец, добавьте `STAThreadAttribute` для `_tWinMain` метод для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7c60a-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="7c60a-144">Этот атрибут сообщает [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , при инициализации [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], следует использовать модель однопотокового подразделения (STA), который необходим для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="7c60a-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="7c60a-145">Создание страницы WPF</span><span class="sxs-lookup"><span data-stu-id="7c60a-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="7c60a-146">Создайте библиотеку DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="7c60a-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="7c60a-147">Часто бывает проще всего создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> как автономное приложение и записи и отладки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часть таким образом.</span><span class="sxs-lookup"><span data-stu-id="7c60a-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="7c60a-148">После этого проект можно преобразовать в библиотеку DLL, щелкнув правой кнопкой мыши проект, щелкнув **свойства**, перейдя в приложение и изменив тип выходных данных на библиотеку классов Windows.</span><span class="sxs-lookup"><span data-stu-id="7c60a-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="7c60a-149">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Проект библиотеки dll, затем может быть объединен с [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта (одно решение, которое содержит два проекта) ― щелкните правой кнопкой мыши решение, выберите **добавить существующий проект**.</span><span class="sxs-lookup"><span data-stu-id="7c60a-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="7c60a-150">Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта, необходимо добавить ссылку:</span><span class="sxs-lookup"><span data-stu-id="7c60a-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="7c60a-151">Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="7c60a-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="7c60a-152">Нажмите кнопку **добавить новую ссылку**.</span><span class="sxs-lookup"><span data-stu-id="7c60a-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="7c60a-153">Щелкните вкладку **Проекты**.  Выберите WPFClock, нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="7c60a-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="7c60a-154">Нажмите кнопку **ОК** для выхода из страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="7c60a-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="7c60a-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="7c60a-155">HwndSource</span></span>  
 <span data-ttu-id="7c60a-156">Далее используется <xref:System.Windows.Interop.HwndSource> вносить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> выглядел как HWND.</span><span class="sxs-lookup"><span data-stu-id="7c60a-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="7c60a-157">Добавьте этот блок кода в файл C++:</span><span class="sxs-lookup"><span data-stu-id="7c60a-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="7c60a-158">это большой фрагмент кода, который требует определенных пояснений.</span><span class="sxs-lookup"><span data-stu-id="7c60a-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="7c60a-159">Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:</span><span class="sxs-lookup"><span data-stu-id="7c60a-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="7c60a-160">Затем определяется функция, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого помещает <xref:System.Windows.Interop.HwndSource> вокруг и возвращает HWND:</span><span class="sxs-lookup"><span data-stu-id="7c60a-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="7c60a-161">Сначала создайте <xref:System.Windows.Interop.HwndSource>, чьи параметры аналогичны параметрам CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="7c60a-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="7c60a-162">После этого создается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] класс содержимого, вызывая его конструктор:</span><span class="sxs-lookup"><span data-stu-id="7c60a-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="7c60a-163">Затем страница соединяется <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="7c60a-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="7c60a-164">И в последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="7c60a-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="7c60a-165">Размещение класса HWND</span><span class="sxs-lookup"><span data-stu-id="7c60a-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="7c60a-166">Теперь, когда имеется HWND, содержащий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов, необходимо поместить этот HWND в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7c60a-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="7c60a-167">Если известно, где размещается HWND, было бы просто передать его размер и расположение для `GetHwnd` функцию, определенную ранее.</span><span class="sxs-lookup"><span data-stu-id="7c60a-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="7c60a-168">Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND.</span><span class="sxs-lookup"><span data-stu-id="7c60a-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="7c60a-169">Можно использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] редактор диалоговых окон для размещения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемента управления "STATIC" место пойти часы («вставьте часы здесь») и использовать его для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов.</span><span class="sxs-lookup"><span data-stu-id="7c60a-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="7c60a-170">Место обработки WM_INITDIALOG использовать `GetDlgItem` для получения HWND для местозаполнителя STATIC:</span><span class="sxs-lookup"><span data-stu-id="7c60a-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="7c60a-171">Затем вычисляется размер и положение местозаполнителя STATIC, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов в этом месте:</span><span class="sxs-lookup"><span data-stu-id="7c60a-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="7c60a-172">Прямоугольник RECT;</span><span class="sxs-lookup"><span data-stu-id="7c60a-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="7c60a-173">Затем местозаполнитель STATIC скрывается:</span><span class="sxs-lookup"><span data-stu-id="7c60a-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="7c60a-174">И создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND в этом расположении часов:</span><span class="sxs-lookup"><span data-stu-id="7c60a-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="7c60a-175">Чтобы сделать это руководство интересным и создать настоящие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов, вам нужно будет создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления часов на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="7c60a-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="7c60a-176">Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="7c60a-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="7c60a-177">Поскольку это руководство о взаимодействии, а не о разработке элементов управления, полный код для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов предоставляется здесь как блок кода, без отдельных указаний по его построению и означает каждая часть.</span><span class="sxs-lookup"><span data-stu-id="7c60a-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="7c60a-178">Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7c60a-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="7c60a-179">Ниже приводится пример разметки:</span><span class="sxs-lookup"><span data-stu-id="7c60a-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="7c60a-180">И сопутствующий код программной части:</span><span class="sxs-lookup"><span data-stu-id="7c60a-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="7c60a-181">Результат выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c60a-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="7c60a-182">![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="7c60a-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="7c60a-183">Чтобы сравнить конечный результат в код, который создал данный снимок, см. [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="7c60a-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c60a-184">См. также</span><span class="sxs-lookup"><span data-stu-id="7c60a-184">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="7c60a-185">Взаимодействие WPF и Win32</span><span class="sxs-lookup"><span data-stu-id="7c60a-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [<span data-ttu-id="7c60a-186">Пример взаимодействия с часами Win32</span><span class="sxs-lookup"><span data-stu-id="7c60a-186">Win32 Clock Interoperation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160051)
