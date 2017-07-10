---
title: "Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 84aadd0ccd7b5c786612d06ca0b46fb5aecd3d2b
ms.openlocfilehash: d068da3253056712f0aab7d536d8faf7c836422b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND

Свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна. В приложениях, ориентированных на .NET Framework версии 4.7, этому свойству можно назначить дескриптор окна (HWND).

В версиях .NET Framework до 4.6.2 для значения, присваиваемого свойству <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, ожидался тип <xref:System.IntPtr>, представляющий расположение в памяти, где находилось значение HWND. В Windows 7 и более ранних версиях операционной системы Windows задание свойству значения `form.Handle` не на что не влияло, но в Windows 8 и более поздних версиях оно приводит к <xref:System.Security.Cryptography> с сообщением "Неверный параметр".

Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может установить значение свойства <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> с помощью следующего кода:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>Последствия

В приложениях, ориентированных на .NET Framework не старше версии 4.7, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>Уменьшение

Разработчики, которые определили, что правильным значением был адрес области памяти, в которой содержалось значение `form.Handle`, могут отказаться от этого изменения в поведении, установив параметру `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` переключателя <xref:System.AppContext> значение `true`:

- путем программной установки переключателей совместимости в экземпляре <xref:System.AppContext>;

- путем добавления следующей строки в раздел `<runtime>` файла app.config:
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

Пользователи, которые хотят изменить поведение приложений, выполняемых на платформе .NET Framework 4.7, но ориентированных на более ранние версии платформы .NET Framework, могут задать переключателю <xref:System.AppContext> значение `false`.
 
## <a name="see-also"></a>См. также

[Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

