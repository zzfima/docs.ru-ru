---
title: Отключить RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186084"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="db634-102">Отключение объекта RealTimeStylus для WPF-приложений</span><span class="sxs-lookup"><span data-stu-id="db634-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="db634-103">Windows Презентация Фонд (WPF) создал в поддержку обработки Windows 7 сенсорный вход.</span><span class="sxs-lookup"><span data-stu-id="db634-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="db634-104">Поддержка поступает через планшет платформы в режиме реального <xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnStylusUp%2A>времени <xref:System.Windows.UIElement.OnStylusMove%2A> стилус ввода как , и события.</span><span class="sxs-lookup"><span data-stu-id="db634-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="db634-105">Windows 7 также обеспечивает многосенсорный вход в качестве WM_TOUCH оконных сообщений Win32.</span><span class="sxs-lookup"><span data-stu-id="db634-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="db634-106">Эти два AA являются взаимоисключающими на одном и том же HWND.</span><span class="sxs-lookup"><span data-stu-id="db634-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="db634-107">Включение сенсорного ввода через планшетную платформу (по умолчанию для приложений WPF) отключит WM_TOUCH сообщений.</span><span class="sxs-lookup"><span data-stu-id="db634-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="db634-108">В результате, чтобы использовать WM_TOUCH для получения сенсорных сообщений из окна WPF, необходимо отключить встроенную поддержку стилуса в WPF.</span><span class="sxs-lookup"><span data-stu-id="db634-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="db634-109">Это применимо в таком сценарии, как окно WPF, в которой размещается компонент, который использует WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="db634-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="db634-110">Чтобы отключить WPF, прослушивающий ввод стилуса, удалите любую поддержку планшета, добавленную окном WPF.</span><span class="sxs-lookup"><span data-stu-id="db634-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db634-111">Пример</span><span class="sxs-lookup"><span data-stu-id="db634-111">Example</span></span>  
 <span data-ttu-id="db634-112">Следующий пример кода показывает, как удалить поддержку планшетной платформы по умолчанию с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="db634-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="db634-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db634-113">See also</span></span>

- [<span data-ttu-id="db634-114">Перехват ввода, осуществляемого пером</span><span class="sxs-lookup"><span data-stu-id="db634-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
