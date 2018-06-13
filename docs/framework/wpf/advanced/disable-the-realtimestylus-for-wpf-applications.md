---
title: Отключение объекта RealTimeStylus для WPF-приложений
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545666"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="9c796-102">Отключение объекта RealTimeStylus для WPF-приложений</span><span class="sxs-lookup"><span data-stu-id="9c796-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="9c796-103">Windows Presentation Foundation (WPF) содержит встроенную поддержку Windows 7 сенсорный ввод. Поддержка проходит по ввод от пера в режиме реального времени платформы планшета как <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, и <xref:System.Windows.UIElement.OnStylusMove%2A> события.</span><span class="sxs-lookup"><span data-stu-id="9c796-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="9c796-104">Windows 7 также предоставляет мультисенсорный ввод как окна WM_TOUCH Win32.</span><span class="sxs-lookup"><span data-stu-id="9c796-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="9c796-105">Эти два API являются взаимоисключающими для того же HWND.</span><span class="sxs-lookup"><span data-stu-id="9c796-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="9c796-106">Включение сенсорного ввода с помощью платформы планшета (по умолчанию для приложений WPF) отключает сообщения WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="9c796-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="9c796-107">В результате Чтобы использовать WM_TOUCH для получения сенсорных сообщений от окна WPF, необходимо отключить встроенную поддержку пера в WPF.</span><span class="sxs-lookup"><span data-stu-id="9c796-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="9c796-108">Это применимо в сценарии, например компонент, который использует WM_TOUCH окна WPF.</span><span class="sxs-lookup"><span data-stu-id="9c796-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="9c796-109">Чтобы отключить прослушивание ввод от пера WPF, удалите всю поддержку планшета, добавленные в окне WPF.</span><span class="sxs-lookup"><span data-stu-id="9c796-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c796-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9c796-110">Example</span></span>  
 <span data-ttu-id="9c796-111">В следующем примере кода показано, как удалить поддержку платформы планшета по умолчанию с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="9c796-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="9c796-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9c796-112">See Also</span></span>  
 [<span data-ttu-id="9c796-113">Перехват ввода, осуществляемого пером</span><span class="sxs-lookup"><span data-stu-id="9c796-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
