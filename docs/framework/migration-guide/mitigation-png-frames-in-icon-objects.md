---
title: "Решение проблемы: кадры PNG в объектах Icon | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Решение проблемы: кадры PNG в объектах Icon
начиная с версии .NET Framework 4.6 метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> успешно преобразует значки с кадрами PNG в объекты <xref:System.Drawing.Bitmap>.  
  
 В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> создает исключение <xref:System.ArgumentOutOfRangeException>, если объект <xref:System.Drawing.Icon> содержит кадры PNG.  
  
## Последствия  
 Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализуется специальная обработка исключения <xref:System.ArgumentOutOfRangeException>, создаваемого при наличии кадров PNG в объекте <xref:System.Drawing.Icon>. При выполнении в .NET Framework 4.6 преобразование проходит успешно, исключение <xref:System.ArgumentOutOfRangeException> больше не создается, и поэтому обработчик исключений больше не вызывается.  
  
### Уменьшение  
 Если такое поведение нежелательно, можно сохранить прежнее поведение, добавив в раздел [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config следующий элемент:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
  
```  
  
 Если файл app.config уже содержит элемент `AppContextSwitchOverrides`, новое значение следует объединить с атрибутом `value` следующим образом:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
  
```  
  
## См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)