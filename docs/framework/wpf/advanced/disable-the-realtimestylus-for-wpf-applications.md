---
title: "Отключение объекта RealTimeStylus для WPF-приложений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Отключение объекта RealTimeStylus для WPF-приложений
Windows Presentation Foundation \(WPF\) имеет встроенную поддержку обработки сенсорного ввода Windows 7. Поддержка проходит по вводу пера в режиме реального времени планшетной платформы как события <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A> и <xref:System.Windows.UIElement.OnStylusMove%2A>.  Windows 7 также предоставляет мультисенсорный ввод как сообщения окна WM\_TOUCH Win32.  Эти два API являются взаимоисключающими при одном и том же HWND.  Включение сенсорного ввода с помощью планшетной платформы \(состояние по умолчанию для приложений WPF\) отключает сообщения WM\_TOUCH.  В результате, чтобы использовать WM\_TOUCH для получения сенсорных сообщений от окна WPF, необходимо отключить встроенную поддержку пера в WPF.  Это применяется в таких сценариях, как, например, окно WPF, содержащее компонент, который использует WM\_TOUCH.  
  
 Чтобы отключить прослушивание WPF ввода пера, следует удалить всю поддержку планшета, добавленную окном WPF.  
  
## Пример  
 В следующем примере кода показывается, как удалить поддержку планшетной платформы, установленную по умолчанию, с помощью отражения.  
  
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
  
## См. также  
 [Перехват ввода, осуществляемого пером](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)