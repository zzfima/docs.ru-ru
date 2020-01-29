---
title: Отключение RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737939"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="a63a6-102">Отключение объекта RealTimeStylus для WPF-приложений</span><span class="sxs-lookup"><span data-stu-id="a63a6-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="a63a6-103">Windows Presentation Foundation (WPF) имеет встроенную поддержку обработки сенсорных входных данных Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a63a6-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="a63a6-104">Поддержка осуществляется с помощью входных данных пера в режиме реального времени на платформе планшета в качестве <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>и <xref:System.Windows.UIElement.OnStylusMove%2A> событий.</span><span class="sxs-lookup"><span data-stu-id="a63a6-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="a63a6-105">Windows 7 также предоставляет ввод с несколькими касаниями в виде оконных сообщений Win32 WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="a63a6-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="a63a6-106">Эти два API являются взаимоисключающими в одном и том же HWND.</span><span class="sxs-lookup"><span data-stu-id="a63a6-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="a63a6-107">Включение сенсорного ввода через платформу планшета (по умолчанию для приложений WPF) отключает WM_TOUCH сообщения.</span><span class="sxs-lookup"><span data-stu-id="a63a6-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="a63a6-108">В результате, чтобы использовать WM_TOUCH для получения сенсорных сообщений из окна WPF, необходимо отключить встроенную поддержку пера в WPF.</span><span class="sxs-lookup"><span data-stu-id="a63a6-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="a63a6-109">Это применимо в таких сценариях, как окно WPF, в котором размещается компонент, использующий WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="a63a6-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="a63a6-110">Чтобы отключить прослушивание WPF для ввода с помощью пера, удалите поддержку планшетов, добавленную в окне WPF.</span><span class="sxs-lookup"><span data-stu-id="a63a6-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a63a6-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a63a6-111">Example</span></span>  
 <span data-ttu-id="a63a6-112">В следующем примере кода показано, как удалить поддержку платформы планшетов по умолчанию с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="a63a6-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a63a6-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a63a6-113">See also</span></span>

- [<span data-ttu-id="a63a6-114">Перехват ввода, осуществляемого пером</span><span class="sxs-lookup"><span data-stu-id="a63a6-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
