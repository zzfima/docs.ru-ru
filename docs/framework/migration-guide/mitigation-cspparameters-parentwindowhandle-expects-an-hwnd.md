---
title: "Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
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
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: 22c258b06a5cc8fa3fec72665d7e413b0cdd11ee
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>Устранение рисков: CspParameters.ParentWindowHandle ожидает HWND

Свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна. В приложениях, ориентированных на .NET Framework версии 4.7, этому свойству можно назначить дескриптор окна (HWND).

В версиях .NET Framework до 4.6.2 для значения, присваиваемого свойству <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, ожидался тип <xref:System.IntPtr>, представляющий расположение в памяти, где находилось значение HWND. В Windows 7 и более ранних версиях операционной системы Windows задание свойству значения `form.Handle` не на что не влияло, но в Windows 8 и более поздних версиях оно приводит к <xref:System.Security.Cryptography> с сообщением "Неверный параметр".

В приложениях, ориентированных на .NET Framework версии 4.7, приложение Windows Forms может задать свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> с помощью похожего кода:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>Последствия

В приложениях, ориентированных на .NET Framework не старше версии 4.7, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>Уменьшение

Разработчики, которые определили, что правильным значением был адрес области памяти, в которой содержалось значение `form.Handle`, могут отказаться от этого изменения в поведении, установив для переключателя <xref:System.Security.AppContext> `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` значение `true`:

- путем программной установки переключателей совместимости в экземпляре [AppContext](assetID:///T:System.Security.AppContext);

- путем добавления следующей строки в раздел `<runtime>` файла app.config:
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

Пользователи, которые хотят изменить поведение приложений, выполняемых на платформе .NET Framework 4.7, но ориентированных на более ранние версии платформы .NET Framework, могут задать переключателю <xref:System.Security.AppContext> значение `false`.
 
## <a name="see-also"></a>См. также

[Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

