---
title: Пошаговое руководство. размещение часов WPF в Win32
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 79f79e42652ca51c409fabb12a572485ad734b35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744895"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="e2122-102">Пошаговое руководство. размещение часов WPF в Win32</span><span class="sxs-lookup"><span data-stu-id="e2122-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="e2122-103">Чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри приложений Win32, используйте <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2122-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="e2122-104">Сначала создайте <xref:System.Windows.Interop.HwndSource>, предоставив ему параметры, аналогичные CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="e2122-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="e2122-105">Затем вы указываете <xref:System.Windows.Interop.HwndSource> о требуемом содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2122-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="e2122-106">Наконец, вы получаете HWND из <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="e2122-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="e2122-107">В этом пошаговом руководстве показано, как создать смешанный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении Win32, которое повторно реализует диалоговое окно **свойств даты и времени** операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e2122-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2122-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="e2122-108">Prerequisites</span></span>

<span data-ttu-id="e2122-109">См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="e2122-110">Применение данного учебника</span><span class="sxs-lookup"><span data-stu-id="e2122-110">How to Use This Tutorial</span></span>

<span data-ttu-id="e2122-111">Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e2122-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="e2122-112">Руководство основано на примере, [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051), но этот пример является отражением конечного продукта.</span><span class="sxs-lookup"><span data-stu-id="e2122-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="e2122-113">В этом учебнике описываются действия, которые необходимо выполнить, как если бы вы начали работу с существующим проектом Win32, возможно, с уже существующим проектом, и вы добавили размещенную [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение.</span><span class="sxs-lookup"><span data-stu-id="e2122-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="e2122-114">Вы можете сравнить конечный продукт с [примером взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="e2122-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="e2122-115">Пошаговое руководство по WPF внутри Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="e2122-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="e2122-116">На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:</span><span class="sxs-lookup"><span data-stu-id="e2122-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Снимок экрана, показывающий диалоговое окно "Свойства даты и времени".](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="e2122-118">Это диалоговое окно можно создать повторно, создав C++ проект Win32 в Visual Studio и используя редактор диалоговых окон, чтобы создать следующее:</span><span class="sxs-lookup"><span data-stu-id="e2122-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Диалоговое окно "Свойства даты и времени создания повторно"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="e2122-120">(Не нужно использовать Visual Studio для использования <xref:System.Windows.Interop.HwndSource>, и вам не нужно использовать C++ для написания программ Win32, но это довольно типичный способ сделать это, и само по себе может стать ступенчатыйным описанием учебника).</span><span class="sxs-lookup"><span data-stu-id="e2122-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="e2122-121">Чтобы добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в диалоговое окно, необходимо выполнить пять конкретных шагов.</span><span class="sxs-lookup"><span data-stu-id="e2122-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="e2122-122">Включите в проекте Win32 вызов управляемого кода ( **/CLR**), изменив параметры проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2122-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="e2122-123">Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="e2122-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="e2122-124">Поставьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="e2122-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="e2122-125">Получите HWND для этого <xref:System.Windows.Controls.Page> используя свойство <xref:System.Windows.Interop.HwndSource.Handle%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2122-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="e2122-126">Использование Win32 для определения места размещения HWND в большом приложении Win32</span><span class="sxs-lookup"><span data-stu-id="e2122-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="e2122-127">/clr</span><span class="sxs-lookup"><span data-stu-id="e2122-127">/clr</span></span>

<span data-ttu-id="e2122-128">Первым шагом является преобразование этого неуправляемого проекта Win32 в тот, который может вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="e2122-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="e2122-129">Используйте параметр компилятора/CLR, который свяжется с необходимыми библиотеками DLL, которые необходимо использовать, и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2122-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="e2122-130">Чтобы включить использование управляемого кода внутри C++ проекта, щелкните правой кнопкой мыши проект win32clock и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e2122-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="e2122-131">На странице свойств **Общие** (по умолчанию) измените поддержку среды clr на `/clr`.</span><span class="sxs-lookup"><span data-stu-id="e2122-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="e2122-132">Затем добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll и UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="e2122-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="e2122-133">(Следующие инструкции предполагают, что операционная система установлена на диске C:.)</span><span class="sxs-lookup"><span data-stu-id="e2122-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="e2122-134">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** и внутри этого диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="e2122-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="e2122-135">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="e2122-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="e2122-136">Щелкните **Добавить новую ссылку**, выберите вкладку Обзор, введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="e2122-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="e2122-137">Повторите то же самое для PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="e2122-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="e2122-138">Повторите то же самое для WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="e2122-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="e2122-139">Повторите то же самое для UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="e2122-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="e2122-140">Повторите то же самое для UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="e2122-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="e2122-141">Щелкните **Добавить новую ссылку**, выберите System. dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e2122-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="e2122-142">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="e2122-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="e2122-143">Наконец, добавьте `STAThreadAttribute` в метод `_tWinMain` для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2122-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="e2122-144">Этот атрибут указывает среде CLR, что при инициализации объектной модели компонента (COM) она должна использовать модель однопотокового подразделения (STA), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e2122-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="e2122-145">Создание страницы WPF</span><span class="sxs-lookup"><span data-stu-id="e2122-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="e2122-146">Затем создается библиотека DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="e2122-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="e2122-147">Зачастую проще всего создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> как автономное приложение, а также написать и отладить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ную часть.</span><span class="sxs-lookup"><span data-stu-id="e2122-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="e2122-148">После этого можно превратить этот проект в библиотеку DLL, щелкнув проект правой кнопкой мыши, выбрав **Свойства**, перейдя к приложению и изменив тип выходных данных на библиотеку классов Windows.</span><span class="sxs-lookup"><span data-stu-id="e2122-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="e2122-149">Затем проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL можно объединить с проектом Win32 (одно решение, содержащее два проекта) — щелкните решение правой кнопкой мыши и выберите **Адд\ексистинг Project (проект**).</span><span class="sxs-lookup"><span data-stu-id="e2122-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="e2122-150">Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] библиотеку DLL из проекта Win32, необходимо добавить ссылку:</span><span class="sxs-lookup"><span data-stu-id="e2122-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="e2122-151">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="e2122-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="e2122-152">Щелкните **Добавить новую ссылку**.</span><span class="sxs-lookup"><span data-stu-id="e2122-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="e2122-153">Перейдите на вкладку **проекты** . Выберите впфклокк и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="e2122-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="e2122-154">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="e2122-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="e2122-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="e2122-155">HwndSource</span></span>

<span data-ttu-id="e2122-156">Затем используйте <xref:System.Windows.Interop.HwndSource>, чтобы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> выглядеть как HWND.</span><span class="sxs-lookup"><span data-stu-id="e2122-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="e2122-157">Добавьте этот блок кода в файл C++:</span><span class="sxs-lookup"><span data-stu-id="e2122-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="e2122-158">это большой фрагмент кода, который требует определенных пояснений.</span><span class="sxs-lookup"><span data-stu-id="e2122-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="e2122-159">Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:</span><span class="sxs-lookup"><span data-stu-id="e2122-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="e2122-160">Затем вы определяете функцию, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ное содержимое, помещает <xref:System.Windows.Interop.HwndSource> вокруг него и возвращает HWND:</span><span class="sxs-lookup"><span data-stu-id="e2122-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="e2122-161">Сначала создайте <xref:System.Windows.Interop.HwndSource>, параметры которого похожи на CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="e2122-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="e2122-162">Затем создайте класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вызвав его конструктор:</span><span class="sxs-lookup"><span data-stu-id="e2122-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="e2122-163">Затем вы подключаете страницу к <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="e2122-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="e2122-164">В последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="e2122-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="e2122-165">Размещение класса HWND</span><span class="sxs-lookup"><span data-stu-id="e2122-165">Positioning the Hwnd</span></span>

<span data-ttu-id="e2122-166">Теперь, когда у вас есть HWND, содержащий часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо разместить HWND в диалоговом окне Win32.</span><span class="sxs-lookup"><span data-stu-id="e2122-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="e2122-167">Если вы знаете, куда разместить HWND, то нужно просто передать этот размер и расположение в определенную ранее функцию `GetHwnd`.</span><span class="sxs-lookup"><span data-stu-id="e2122-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="e2122-168">Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND.</span><span class="sxs-lookup"><span data-stu-id="e2122-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="e2122-169">Вы можете использовать редактор диалоговых окон Visual Studio для размещения статического элемента управления Win32 в том месте, где нужно добавить часы ("вставить часы здесь"), и использовать его для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов.</span><span class="sxs-lookup"><span data-stu-id="e2122-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="e2122-170">При обработке WM_INITDIALOG используется `GetDlgItem` для получения HWND для прототипа STATIC:</span><span class="sxs-lookup"><span data-stu-id="e2122-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="e2122-171">Затем вы вычисляете размер и позицию этого заполнителя STATIC, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в это место:</span><span class="sxs-lookup"><span data-stu-id="e2122-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="e2122-172">Прямоугольник RECT;</span><span class="sxs-lookup"><span data-stu-id="e2122-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="e2122-173">Затем местозаполнитель STATIC скрывается:</span><span class="sxs-lookup"><span data-stu-id="e2122-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="e2122-174">Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND часов в этом расположении:</span><span class="sxs-lookup"><span data-stu-id="e2122-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="e2122-175">Чтобы сделать этот учебник интересным и создать реальный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, на этом этапе необходимо создать элемент управления часами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2122-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="e2122-176">Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="e2122-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="e2122-177">Поскольку в этом учебнике рассматривается взаимодействие, а не проектирование элементов управления, полный код для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов предоставляется здесь в виде блока кода без дискретных инструкций по его созданию или по каждой части.</span><span class="sxs-lookup"><span data-stu-id="e2122-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="e2122-178">Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e2122-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="e2122-179">Ниже приводится пример разметки:</span><span class="sxs-lookup"><span data-stu-id="e2122-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="e2122-180">И сопутствующий код программной части:</span><span class="sxs-lookup"><span data-stu-id="e2122-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="e2122-181">Результат выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2122-181">The final result looks like:</span></span>

![Диалоговое окно «Свойства даты и времени последнего результата»](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="e2122-183">Чтобы сравнить конечный результат с кодом, созданным на этом снимке экрана, см. [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="e2122-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2122-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2122-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="e2122-185">Взаимодействие WPF и Win32</span><span class="sxs-lookup"><span data-stu-id="e2122-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="e2122-186">Пример взаимодействия с часами Win32</span><span class="sxs-lookup"><span data-stu-id="e2122-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
