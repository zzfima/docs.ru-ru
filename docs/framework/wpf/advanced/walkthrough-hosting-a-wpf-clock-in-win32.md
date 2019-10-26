---
title: Пошаговое руководство. Размещение часов WPF в Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 42ed51a1a1ce59b6a3cc3319d86d3a7445403ce4
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919741"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="9c3fb-102">Пошаговое руководство. Размещение часов WPF в Win32</span><span class="sxs-lookup"><span data-stu-id="9c3fb-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="9c3fb-103">Чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложениях, используйте <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="9c3fb-104">Сначала создайте <xref:System.Windows.Interop.HwndSource>, предоставив ему параметры, аналогичные CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="9c3fb-105">Затем вы указываете <xref:System.Windows.Interop.HwndSource> о требуемом содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="9c3fb-106">Наконец, вы получаете HWND из <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="9c3fb-107">В этом пошаговом руководстве показано, как создать смешанный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении, которое повторно реализует диалоговое окно **свойств даты и времени** операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c3fb-108">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="9c3fb-108">Prerequisites</span></span>

<span data-ttu-id="9c3fb-109">См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="9c3fb-110">Как использовать этот учебник</span><span class="sxs-lookup"><span data-stu-id="9c3fb-110">How to Use This Tutorial</span></span>

<span data-ttu-id="9c3fb-111">Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="9c3fb-112">Руководство основано на примере, [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051), но этот пример является отражением конечного продукта.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="9c3fb-113">В этом учебнике описываются действия, которые необходимо выполнить, как если бы вы начали работу с существующим [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] собственным проектом, возможно, с уже существующим проектом, и вы добавили в приложение размещенную [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="9c3fb-114">Вы можете сравнить конечный продукт с [примером взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="9c3fb-115">Пошаговое руководство по WPF внутри Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="9c3fb-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="9c3fb-116">На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Снимок экрана, показывающий диалоговое окно "Свойства даты и времени".](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="9c3fb-118">Это диалоговое окно можно создать повторно, создав C++ проект Win32 в Visual Studio и используя редактор диалоговых окон, чтобы создать следующее:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Диалоговое окно "Свойства даты и времени создания повторно"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="9c3fb-120">(Не нужно использовать Visual Studio для использования <xref:System.Windows.Interop.HwndSource>, и вам не нужно использовать C++ для написания[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ных программ, но это довольно типичный способ сделать это, и само по себе ступенчатый в учебнике).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="9c3fb-121">Чтобы добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в диалоговое окно, необходимо выполнить пять конкретных шагов.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="9c3fb-122">Разрешите [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекту вызывать управляемый код ( **/CLR**), изменив параметры проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="9c3fb-123">Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="9c3fb-124">Поставьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="9c3fb-125">Получите HWND для этого <xref:System.Windows.Controls.Page> используя свойство <xref:System.Windows.Interop.HwndSource.Handle%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="9c3fb-126">Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], чтобы решить, куда поместить HWND в более крупном [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="9c3fb-127">/clr</span><span class="sxs-lookup"><span data-stu-id="9c3fb-127">/clr</span></span>

<span data-ttu-id="9c3fb-128">Первым шагом является преобразование неуправляемого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта в тот, который может вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="9c3fb-129">Используйте параметр компилятора/CLR, который свяжется с необходимыми библиотеками DLL, которые необходимо использовать, и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="9c3fb-130">Чтобы включить использование управляемого кода внутри C++ проекта, щелкните правой кнопкой мыши проект win32clock и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="9c3fb-131">На странице свойств **Общие** (по умолчанию) измените поддержку среды clr на `/clr`.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="9c3fb-132">Затем добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll и UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="9c3fb-133">(Следующие инструкции предполагают, что операционная система установлена на диске C:.)</span><span class="sxs-lookup"><span data-stu-id="9c3fb-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="9c3fb-134">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** и внутри этого диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="9c3fb-135">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="9c3fb-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="9c3fb-136">Щелкните **Добавить новую ссылку**, выберите вкладку Обзор, введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="9c3fb-137">Повторите то же самое для PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="9c3fb-138">Повторите то же самое для WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="9c3fb-139">Повторите то же самое для UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="9c3fb-140">Повторите то же самое для UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="9c3fb-141">Щелкните **Добавить новую ссылку**, выберите System. dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="9c3fb-142">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="9c3fb-143">Наконец, добавьте `STAThreadAttribute` в метод `_tWinMain` для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="9c3fb-144">Этот атрибут указывает среде CLR, что при инициализации объектной модели компонента (COM) она должна использовать модель однопотокового подразделения (STA), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="9c3fb-145">Создание страницы WPF</span><span class="sxs-lookup"><span data-stu-id="9c3fb-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="9c3fb-146">Затем создается библиотека DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="9c3fb-147">Зачастую проще всего создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> как автономное приложение, а также написать и отладить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ную часть.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="9c3fb-148">После этого можно превратить этот проект в библиотеку DLL, щелкнув проект правой кнопкой мыши, выбрав **Свойства**, перейдя к приложению и изменив тип выходных данных на библиотеку классов Windows.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="9c3fb-149">Проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL можно объединить с [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ным проектом (одно решение, содержащее два проекта) — щелкните решение правой кнопкой мыши и выберите **Адд\ексистинг Project (проект**).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="9c3fb-150">Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL из проекта [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], необходимо добавить ссылку:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="9c3fb-151">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="9c3fb-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="9c3fb-152">Щелкните **Добавить новую ссылку**.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="9c3fb-153">Перейдите на вкладку **проекты** . Выберите впфклокк и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="9c3fb-154">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="9c3fb-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="9c3fb-155">HwndSource</span></span>

<span data-ttu-id="9c3fb-156">Затем используйте <xref:System.Windows.Interop.HwndSource>, чтобы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> выглядеть как HWND.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="9c3fb-157">Добавьте этот блок кода в файл C++:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-157">You add this block of code to a C++ file:</span></span>

```cpp
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

 <span data-ttu-id="9c3fb-158">это большой фрагмент кода, который требует определенных пояснений.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="9c3fb-159">Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="9c3fb-160">Затем вы определяете функцию, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ное содержимое, помещает <xref:System.Windows.Interop.HwndSource> вокруг него и возвращает HWND:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="9c3fb-161">Сначала создайте <xref:System.Windows.Interop.HwndSource>, параметры которого похожи на CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="9c3fb-162">Затем создайте класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вызвав его конструктор:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="9c3fb-163">Затем вы подключаете страницу к <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="9c3fb-164">В последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="9c3fb-165">Размещение класса HWND</span><span class="sxs-lookup"><span data-stu-id="9c3fb-165">Positioning the Hwnd</span></span>

<span data-ttu-id="9c3fb-166">Теперь, когда у вас есть HWND, содержащий часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо разместить HWND в диалоговом окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="9c3fb-167">Если вы знаете, куда разместить HWND, то нужно просто передать этот размер и расположение в определенную ранее функцию `GetHwnd`.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="9c3fb-168">Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="9c3fb-169">Вы можете использовать редактор диалоговых окон Visual Studio, чтобы поместить [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] статический элемент управления, в который нужно добавить часы ("вставить часы здесь"), и использовать его для размещения часов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-169">You can use the Visual Studio dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="9c3fb-170">При обработке WM_INITDIALOG используется `GetDlgItem` для получения HWND для прототипа STATIC:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="9c3fb-171">Затем вы вычисляете размер и позицию этого заполнителя STATIC, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в это место:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="9c3fb-172">Прямоугольник RECT;</span><span class="sxs-lookup"><span data-stu-id="9c3fb-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="9c3fb-173">Затем местозаполнитель STATIC скрывается:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="9c3fb-174">Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND часов в этом расположении:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="9c3fb-175">Чтобы сделать этот учебник интересным и создать реальный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, на этом этапе необходимо создать элемент управления часами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3fb-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="9c3fb-176">Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="9c3fb-177">Поскольку в этом учебнике рассматривается взаимодействие, а не проектирование элементов управления, полный код для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов предоставляется здесь в виде блока кода без дискретных инструкций по его созданию или по каждой части.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="9c3fb-178">Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9c3fb-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="9c3fb-179">Ниже приводится пример разметки:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="9c3fb-180">И сопутствующий код программной части:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="9c3fb-181">Результат выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c3fb-181">The final result looks like:</span></span>

![Диалоговое окно «Свойства даты и времени последнего результата»](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="9c3fb-183">Чтобы сравнить конечный результат с кодом, созданным на этом снимке экрана, см. [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="9c3fb-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c3fb-184">См. также</span><span class="sxs-lookup"><span data-stu-id="9c3fb-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="9c3fb-185">Взаимодействие WPF и Win32</span><span class="sxs-lookup"><span data-stu-id="9c3fb-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="9c3fb-186">Пример взаимодействия с часами Win32</span><span class="sxs-lookup"><span data-stu-id="9c3fb-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
