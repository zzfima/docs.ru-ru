---
title: Отключение объекта RealTimeStylus для WPF-приложений
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: acae177e1c49a6a1161bcf48f8e2e8ac1bfe13b8
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991845"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Отключение объекта RealTimeStylus для WPF-приложений
Windows Presentation Foundation (WPF) имеет встроенную поддержку обработки сенсорных входных данных Windows 7. Поддержка осуществляется с помощью входных данных пера в режиме реального времени на платформе <xref:System.Windows.UIElement.OnStylusDown%2A>планшета в <xref:System.Windows.UIElement.OnStylusMove%2A> качестве событий, <xref:System.Windows.UIElement.OnStylusUp%2A>и. Windows 7 также предоставляет ввод с несколькими касаниями в виде оконных сообщений Win32 WM_TOUCH. Эти два API являются взаимоисключающими в одном и том же HWND. Включение сенсорного ввода через платформу планшета (по умолчанию для приложений WPF) отключает сообщения WM_TOUCH. В результате, чтобы использовать WM_TOUCH для получения сенсорных сообщений из окна WPF, необходимо отключить встроенную поддержку пера в WPF. Это применимо в таких сценариях, как окно WPF, в котором размещается компонент, использующий WM_TOUCH.  
  
 Чтобы отключить прослушивание WPF для ввода с помощью пера, удалите поддержку планшетов, добавленную в окне WPF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как удалить поддержку платформы планшетов по умолчанию с помощью отражения.  
  
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
  
## <a name="see-also"></a>См. также

- [Перехват ввода, осуществляемого пером](intercepting-input-from-the-stylus.md)
