---
title: Пошаговое руководство. Размещение часов WPF в Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 98e48060bbb82764e1e541797c666ca33f247c39
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400475"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="c16a5-102">Пошаговое руководство. Размещение часов WPF в Win32</span><span class="sxs-lookup"><span data-stu-id="c16a5-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="c16a5-103">Чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутренние [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения, используйте <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий ваше [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое.</span><span class="sxs-lookup"><span data-stu-id="c16a5-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="c16a5-104">Сначала создайте <xref:System.Windows.Interop.HwndSource>, предоставив ему параметры, аналогичные CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="c16a5-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="c16a5-105">Затем вы узнаете <xref:System.Windows.Interop.HwndSource> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] о содержимом, которое вы хотите поместить в него.</span><span class="sxs-lookup"><span data-stu-id="c16a5-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="c16a5-106">Наконец, вы получаете HWND из <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="c16a5-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="c16a5-107">В этом пошаговом руководстве показано, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] как [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] создать смешанное приложение, которое повторно реализует диалоговое окно **свойств даты и времени** операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c16a5-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c16a5-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c16a5-108">Prerequisites</span></span>

<span data-ttu-id="c16a5-109">См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="c16a5-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="c16a5-110">Как использовать этот учебник</span><span class="sxs-lookup"><span data-stu-id="c16a5-110">How to Use This Tutorial</span></span>

<span data-ttu-id="c16a5-111">Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c16a5-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="c16a5-112">Руководство основано на примере, [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051), но этот пример является отражением конечного продукта.</span><span class="sxs-lookup"><span data-stu-id="c16a5-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="c16a5-113">В этом руководстве описаны действия, которые необходимо выполнить, как если бы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] вы начали работу с существующим проектом, возможно, с уже существующим проектом, и вы добавили приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенное в приложении.</span><span class="sxs-lookup"><span data-stu-id="c16a5-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="c16a5-114">Вы можете сравнить конечный продукт с [примером взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="c16a5-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="c16a5-115">Пошаговое руководство по WPF внутри Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="c16a5-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="c16a5-116">На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:</span><span class="sxs-lookup"><span data-stu-id="c16a5-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Снимок экрана, показывающий диалоговое окно "Свойства даты и времени".](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="c16a5-118">Это диалоговое окно можно создать повторно, создав C++ проект Win32 в Visual Studio и используя редактор диалоговых окон, чтобы создать следующее:</span><span class="sxs-lookup"><span data-stu-id="c16a5-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Диалоговое окно "Свойства даты и времени создания повторно"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="c16a5-120">(Использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для использования <xref:System.Windows.Interop.HwndSource>не требуется, и вам не нужно использовать C++ для написания [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программ, но это довольно типичный способ сделать это, и само по себе оно хорошо послужит в ступенчатый руководстве).</span><span class="sxs-lookup"><span data-stu-id="c16a5-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="c16a5-121">Чтобы добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в диалоговое окно, необходимо выполнить пять определенных подшагов.</span><span class="sxs-lookup"><span data-stu-id="c16a5-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="c16a5-122">Разрешить проекту вызывать управляемый код (/CLR), изменяя параметры проекта [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]в. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16a5-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="c16a5-123">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Создайте<xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="c16a5-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="c16a5-124">Вставьте его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в .<xref:System.Windows.Interop.HwndSource></span><span class="sxs-lookup"><span data-stu-id="c16a5-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="c16a5-125">Получите HWND для этого <xref:System.Windows.Controls.Page> <xref:System.Windows.Interop.HwndSource.Handle%2A> с помощью свойства.</span><span class="sxs-lookup"><span data-stu-id="c16a5-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="c16a5-126">Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , чтобы решить, куда поместить HWND в более крупном [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении.</span><span class="sxs-lookup"><span data-stu-id="c16a5-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="c16a5-127">/clr</span><span class="sxs-lookup"><span data-stu-id="c16a5-127">/clr</span></span>

<span data-ttu-id="c16a5-128">Первым шагом является преобразование этого неуправляемого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта в другой, который может вызывать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="c16a5-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="c16a5-129">Используйте параметр компилятора/CLR, который свяжется с необходимыми библиотеками DLL, которые необходимо использовать, и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c16a5-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="c16a5-130">Чтобы включить использование управляемого кода в C++ проекте, выполните следующие действия. Щелкните правой кнопкой мыши проект win32clock и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c16a5-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="c16a5-131">На странице свойств **Общие** (по умолчанию) измените поддержку среды CLR на `/clr`.</span><span class="sxs-lookup"><span data-stu-id="c16a5-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="c16a5-132">Затем добавьте ссылки на библиотеки DLL, необходимые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]для: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll и UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="c16a5-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="c16a5-133">(Следующие инструкции предполагают, что операционная система установлена на диске C:.)</span><span class="sxs-lookup"><span data-stu-id="c16a5-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="c16a5-134">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** и внутри этого диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="c16a5-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="c16a5-135">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="c16a5-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="c16a5-136">Щелкните **Добавить новую ссылку**, выберите вкладку Обзор, введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="c16a5-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="c16a5-137">Повторите для PresentationFramework. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="c16a5-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="c16a5-138">Повторите для WindowsBase. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="c16a5-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="c16a5-139">Повторите для UIAutomationTypes. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="c16a5-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="c16a5-140">Повторите для UIAutomationProvider. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="c16a5-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="c16a5-141">Щелкните **Добавить новую ссылку**, выберите System. dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c16a5-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="c16a5-142">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="c16a5-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="c16a5-143">Наконец, добавьте `STAThreadAttribute` `_tWinMain` в метод для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c16a5-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="c16a5-144">Этот атрибут указывает среде CLR, что при инициализации [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]она должна использовать модель однопотокового подразделения (STA), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="c16a5-144">This attribute tells the common language runtime (CLR) that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="c16a5-145">Создание страницы WPF</span><span class="sxs-lookup"><span data-stu-id="c16a5-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="c16a5-146">Затем создается библиотека DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="c16a5-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="c16a5-147">Зачастую проще создать приложение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> качестве автономного приложения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] а также написать и отладить часть таким образом.</span><span class="sxs-lookup"><span data-stu-id="c16a5-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="c16a5-148">После этого можно превратить этот проект в библиотеку DLL, щелкнув проект правой кнопкой мыши, выбрав **Свойства**, перейдя к приложению и изменив тип выходных данных на библиотеку классов Windows.</span><span class="sxs-lookup"><span data-stu-id="c16a5-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="c16a5-149">Затем проект [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] DLL можно объединить с проектом (одно решение, содержащее два проекта) — щелкните решение правой кнопкой мыши и выберите **адд\ексистинг Project (проект**). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16a5-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="c16a5-150">Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] библиотеку DLL [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] из проекта, необходимо добавить ссылку:</span><span class="sxs-lookup"><span data-stu-id="c16a5-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="c16a5-151">Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .</span><span class="sxs-lookup"><span data-stu-id="c16a5-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="c16a5-152">Щелкните **Добавить новую ссылку**.</span><span class="sxs-lookup"><span data-stu-id="c16a5-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="c16a5-153">Щелкните вкладку **Проекты**. Выберите WPFClock, нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="c16a5-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="c16a5-154">Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.</span><span class="sxs-lookup"><span data-stu-id="c16a5-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="c16a5-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="c16a5-155">HwndSource</span></span>

<span data-ttu-id="c16a5-156">Затем используйте <xref:System.Windows.Interop.HwndSource> , чтобы сделать его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> похожим на HWND.</span><span class="sxs-lookup"><span data-stu-id="c16a5-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="c16a5-157">Добавьте этот блок кода в файл C++:</span><span class="sxs-lookup"><span data-stu-id="c16a5-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="c16a5-158">это большой фрагмент кода, который требует определенных пояснений.</span><span class="sxs-lookup"><span data-stu-id="c16a5-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="c16a5-159">Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:</span><span class="sxs-lookup"><span data-stu-id="c16a5-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="c16a5-160">Затем вы определяете функцию, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, <xref:System.Windows.Interop.HwndSource> помещает вокруг нее и возвращает HWND:</span><span class="sxs-lookup"><span data-stu-id="c16a5-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="c16a5-161">Сначала создайте объект <xref:System.Windows.Interop.HwndSource>, параметры которого похожи на CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="c16a5-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="c16a5-162">Затем создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] класс содержимого, вызвав его конструктор:</span><span class="sxs-lookup"><span data-stu-id="c16a5-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="c16a5-163">Затем вы подключаете страницу к <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="c16a5-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="c16a5-164">В последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="c16a5-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="c16a5-165">Размещение класса HWND</span><span class="sxs-lookup"><span data-stu-id="c16a5-165">Positioning the Hwnd</span></span>

<span data-ttu-id="c16a5-166">Теперь, когда у вас есть HWND, содержащий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, необходимо разместить HWND [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] внутри диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="c16a5-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="c16a5-167">Если вы знаете, куда разместить HWND, то нужно просто передать этот размер и расположение в `GetHwnd` определенную ранее функцию.</span><span class="sxs-lookup"><span data-stu-id="c16a5-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="c16a5-168">Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND.</span><span class="sxs-lookup"><span data-stu-id="c16a5-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="c16a5-169">Можно использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] редактор диалоговых окон, чтобы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] поместить статический элемент управления в место, где нужно добавить часы ("вставить часы здесь"), и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использовать его для позиционирования часов.</span><span class="sxs-lookup"><span data-stu-id="c16a5-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="c16a5-170">При обработке WM_INITDIALOG используется `GetDlgItem` для получения HWND для прототипа static:</span><span class="sxs-lookup"><span data-stu-id="c16a5-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="c16a5-171">Затем вы вычисляете размер и позицию этого заполнителя static, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в это место:</span><span class="sxs-lookup"><span data-stu-id="c16a5-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="c16a5-172">Прямоугольник RECT;</span><span class="sxs-lookup"><span data-stu-id="c16a5-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="c16a5-173">Затем местозаполнитель STATIC скрывается:</span><span class="sxs-lookup"><span data-stu-id="c16a5-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="c16a5-174">И создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND часов в этом расположении:</span><span class="sxs-lookup"><span data-stu-id="c16a5-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="c16a5-175">Чтобы сделать этот учебник интересным и получить реальные [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, на этом этапе необходимо [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создать элемент управления часами.</span><span class="sxs-lookup"><span data-stu-id="c16a5-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="c16a5-176">Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="c16a5-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="c16a5-177">Так как в этом учебнике рассматривается взаимодействие, а не структура элемента управления, полный код [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для часов предоставляется здесь в виде блока кода без отдельных инструкций по его созданию или по каждой части.</span><span class="sxs-lookup"><span data-stu-id="c16a5-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="c16a5-178">Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c16a5-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="c16a5-179">Ниже приводится пример разметки:</span><span class="sxs-lookup"><span data-stu-id="c16a5-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="c16a5-180">И сопутствующий код программной части:</span><span class="sxs-lookup"><span data-stu-id="c16a5-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="c16a5-181">Результат выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c16a5-181">The final result looks like:</span></span>

![Диалоговое окно «Свойства даты и времени последнего результата»](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="c16a5-183">Чтобы сравнить конечный результат с кодом, созданным на этом снимке экрана, см. [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="c16a5-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="c16a5-184">См. также</span><span class="sxs-lookup"><span data-stu-id="c16a5-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="c16a5-185">Взаимодействие WPF и Win32</span><span class="sxs-lookup"><span data-stu-id="c16a5-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="c16a5-186">Пример взаимодействия с часами Win32</span><span class="sxs-lookup"><span data-stu-id="c16a5-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
