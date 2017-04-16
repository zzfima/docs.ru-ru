---
title: "Registering Assemblies with COM | Microsoft Docs"
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
  - "COM interop, registering assemblies"
  - "unregistering assemblies"
  - "interoperation with unmanaged code, registering assemblies"
  - "registering assemblies"
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Registering Assemblies with COM
С целью регистрации или отмены регистрации сборки для использования с COM можно использовать средство командной строки, называющееся [программой регистрации сборок \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).  Программа Regasm.exe добавляет сведения о классе в системный реестр, поэтому модели COM клиенты могут использовать класс .NET Framework прозрачно.  Класс <xref:System.Runtime.InteropServices.RegistrationServices> обеспечивает эквивалентные функциональные возможности подписания.  
  
 Прежде чем управляемый компонент может быть активирован COM\-клиентом, он должен быть зарегистрирован в системном реестре Windows.  В следующей таблице приведены разделы, которые программа Regasm.exe обычно добавляет в реестр Windows.  \(000000 означает фактическое значение GUID.\)  
  
|GUID|Описание|Раздел реестра|  
|----------|--------------|--------------------|  
|CLSID|Идентификатор класса|HKEY\_CLASSES\_ROOT\\CLSID\\{000…000}|  
|идентификатор интерфейса \(IID\)|Идентификатор интерфейса|HKEY\_CLASSES\_ROOT\\Interface\\{000…000}|  
|LIBID|Идентификатор библиотеки|HKEY\_CLASSES\_ROOT\\TypeLib\\{000…000}|  
|ProgID|Программный идентификатор|HKEY\_CLASSES\_ROOT\\000…000|  
  
 В разделе HKCR\\CLSID\\{0000…0000} в качестве значения по умолчанию установлено значение ProgID класса и добавлено два новых именованных значения, Class и Assembly.  Среда выполнения читает в реестре значение Assembly и передает его распознавателю сборок.   сборок пытается найти сборку в соответствии с полученными о ней сведениями — по имени и номеру версии.  Чтобы распознаватель сборок мог найти сборку, она должна находиться в одном из следующих мест:  
  
-   В глобальном кэше сборок \(должна быть сборкой со строгими именами\).  
  
-   В папке приложения.  Сборки, загруженные из папки приложения, доступны только для этого приложения.  
  
-   В пути к файлу, заданном параметром **\/codebase** программы Regasm.exe.  
  
 Программа Regasm.exe также создает раздел InProcServer32 в разделе HKCR\\CLSID\\{0000…0000}.  В качестве значения по умолчанию для этого раздела установлено имя библиотеки DLL, которая инициализирует среду CLR \(Mscoree.dll\).  
  
## Просмотр записей реестра  
 Для создания экземпляра любого класса .NET Framework COM\-взаимодействие обеспечивает реализацию стандартной фабрики классов.  Для получения фабрики классов и создания объектов клиенты могут вызывать функцию **DllGetClassObject** управляемой DLL точно так же, как и для любого другого COM\-компонента.  
  
 Для подраздела `InprocServer32`, указывающая, что вместо традиционной библиотеки типов модели COM отображает ссылку на библиотеку Mscoree.dll, что среда CLR создает управляемый объект.  
  
## См. также  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [How to: Reference .NET Types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/ru-ru/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/ru-ru/fb63564c-c1b9-4655-a094-a235625882ce)