---
title: "Marshaling Strings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "marshaling, samples"
  - "platform invoke, marshaling data"
  - "data marshaling, strings"
  - "data marshaling, samples"
  - "data marshaling, platform invoke"
  - "marshaling. strings"
  - "marshaling, platform invoke"
  - "sample applications [.NET Framework], marshaling strings"
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Marshaling Strings
При вызове неуправляемого кода происходит копирование строковых параметров, а затем, при необходимости, выполняется их преобразование из формата .NET Framework \(Юникод\) в неуправляемый формат \(ANSI\).  В силу того, что управляемые строки являются неизменяемыми, при вызове неуправляемого кода они не копируются из неуправляемой памяти в управляемую во время возврата из функции.  
  
 В следующей таблице представлены параметры маршалинга строк, описание их применения и ссылки на соответствующие примеры .NET Framework.  
  
|Строка.|Описание|Пример|  
|-------------|--------------|------------|  
|По значению.|Передача строк как параметров In.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Как результат.|Возврат строк из неуправляемого кода.|[Строки](http://msdn.microsoft.com/ru-ru/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|По ссылке.|Передача строк как параметров In\/Out с помощью <xref:System.Text.StringBuilder>.|[Буферы](http://msdn.microsoft.com/ru-ru/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|В структуре по значению.|Передача строк в структуре как параметра In.|[Структуры](http://msdn.microsoft.com/ru-ru/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|В структуре по ссылке **\(char\*\)**.|Передача строк в структуре, являющейся параметром In\/Out.  Неуправляемая функция ожидает указатель на символьный буфер, размер буфера является членом структуры.|[Строки](http://msdn.microsoft.com/ru-ru/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|В структуре по ссылке **\(char\[\]\)**.|Передача строк в структуре, являющейся параметром In\/Out.  Неуправляемая функция ожидает вложенный символьный буфер.|[OSInfo](http://msdn.microsoft.com/ru-ru/69d89067-507b-41fe-859d-30bf3ff29455)|  
|В классе по значению **\(char\*\)**.|Передача строк в классе \(класс представляет собой параметр In\/Out\).  Неуправляемая функция ожидает указатель на символьный буфер.|[OpenFileDlg](http://msdn.microsoft.com/ru-ru/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|В классе по значению **\(char\[\]\)**.|Передача строк в классе \(класс представляет собой параметр In\/Out\).  Неуправляемая функция ожидает вложенный символьный буфер.|[OSInfo](http://msdn.microsoft.com/ru-ru/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Как массив строк по значению.|Создание массива строк, передаваемого по значению.|[Массивы](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Как массив структур, содержащий строки по значению.|Создание массива структур, содержащего строки. Массив передается по значению.|[Массивы](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## См. также  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/ru-ru/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshaling Classes, Structures, and Unions](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshaling Arrays of Types](http://msdn.microsoft.com/ru-ru/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/ru-ru/a915c948-54e9-4d0f-a525-95a77fd8ed70)