---
title: "Exposing .NET Framework Components to COM | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Exposing .NET Framework Components to COM
Для разработчиков написание типа .NET и использование этого типа из неуправляемого программного кода — это разные операции.  В этом разделе дается несколько советов по написанию управляемого кода, взаимодействующего с COM\-клиентами.  
  
-   [Уточнение типов .NET для взаимодействия](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Все управляемые типы, методы, свойства, поля и события, доступ к которым нужно предоставить COM\-объектам, должны быть открытыми.  Типы должны использовать открытый конструктор по умолчанию, представляющий собой единственный конструктор, который можно вызывать с помощью COM.  
  
-   [Применение атрибутов взаимодействия](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     Настраиваемые атрибуты в управляемом коде могут расширять возможности взаимодействия для соответствующего компонента.  
  
-   [Упаковка сборки для модели COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     Разработчикам COM\-приложений могут потребоваться пояснения, касающиеся процедур обращения к сборке и ее развертывания.  
  
 Кроме того, в этом разделе определяются задачи, связанные с использованием управляемого типа из COM\-клиента.  
  
#### Использование управляемого типа из модели COM  
  
1.  [Регистрация сборок в COM\-приложении](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     Типы в сборке \(и библиотеки типов\) должны быть зарегистрированы во время разработки.  Если программа установки не регистрирует сборку автоматически, разработчики COM\-приложений должны использовать для регистрации программу Regasm.exe.  
  
2.  [Обращение к типам .NET из COM\-приложений](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Для обращения к типам в сборке разработчики COM\-приложений могут использовать свои обычные средства и способы.  
  
3.  [Вызов объекта .NET](http://msdn.microsoft.com/ru-ru/40c9626c-aea6-4bad-b8f0-c1de462efd33).  
  
     Разработчики COM\-приложений могут вызывать методы объекта .NET таким же образом, как и методы любого неуправляемого типа.  Например, API\-интерфейс **CoCreateInstance** модели COM активирует объекты .NET.  
  
4.  [Развертывание приложения для доступа COM](http://msdn.microsoft.com/ru-ru/fb63564c-c1b9-4655-a094-a235625882ce).  
  
     Сборка со строгим именем может быть установлена в глобальном кэше сборок и требует подписи издателя.  Сборки, для которых не задан режим строгих имен, должны быть установлены в папке каталоге приложения клиента.  
  
## См. также  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [COM Interop Sample: COM Client and .NET Server](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)