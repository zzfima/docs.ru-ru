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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Отключение объекта RealTimeStylus для WPF-приложений

Windows Презентация Фонд (WPF) создал в поддержку обработки Windows 7 сенсорный вход. Поддержка поступает через планшет платформы в режиме реального <xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnStylusUp%2A>времени <xref:System.Windows.UIElement.OnStylusMove%2A> стилус ввода как , и события. Windows 7 также обеспечивает многосенсорный вход в качестве WM_TOUCH оконных сообщений Win32. Эти два AA являются взаимоисключающими на одном и том же HWND. Включение сенсорного ввода через планшетную платформу (по умолчанию для приложений WPF) отключит WM_TOUCH сообщений. В результате, чтобы использовать WM_TOUCH для получения сенсорных сообщений из окна WPF, необходимо отключить встроенную поддержку стилуса в WPF. Это применимо в таком сценарии, как окно WPF, в которой размещается компонент, который использует WM_TOUCH.  
  
 Чтобы отключить WPF, прослушивающий ввод стилуса, удалите любую поддержку планшета, добавленную окном WPF.  
  
## <a name="example"></a>Пример  
 Следующий пример кода показывает, как удалить поддержку планшетной платформы по умолчанию с помощью отражения.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Перехват ввода, осуществляемого пером](intercepting-input-from-the-stylus.md)
