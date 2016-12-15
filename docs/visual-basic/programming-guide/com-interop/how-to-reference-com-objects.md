---
title: "Практическое руководство. Ссылка на COM-объект в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM-взаимодействие, создание ссылок на COM-объекты"
  - "COM-объекты, создание ссылок"
  - "сборки взаимодействия"
  - "объекты [Visual Basic], создание ссылок"
  - "создание ссылок на объекты, COM-объекты из Visual Basic"
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Ссылка на COM-объект в Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] добавление ссылки на COM\-объекты, имеющие библиотеки типов, требует создания сборки взаимодействия для библиотеки COM.  Ссылки на члены объекта COM направляются в сборку взаимодействия, а затем пересылаются в актуальный объект COM.  Отклики от объекта COM направляются в сборку взаимодействия и пересылаются в приложение [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 Ссылку на COM\-объект можно создать без использования сборки взаимодействия путем встраивания сведения о типе для COM\-объекта в сборку .NET.  Чтобы встроить сведения о типе, присвойте свойству `Embed Interop Types` значение `True` для ссылки на COM\-объект.  При использовании компилятора командной строки для создания ссылки на библиотеку COM следует воспользоваться параметром `/link`.  Дополнительные сведения см. в разделе [\/link](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки \(IDE\).  При работе в командной строке можно использовать программу Tlbimp для создания сборок взаимодействия вручную.  
  
### Добавить ссылки на объекты COM  
  
1.  В меню **Проект** выберите **Добавить ссылку** и откройте вкладку **COM** в диалоговом окне.  
  
2.  Из списка объектов COM выберите нужный компонент.  
  
3.  Для упрощения доступа к сборке взаимодействия добавьте инструкцию `Imports` в начале класса или модуля, в котором будет использоваться объект COM.  В следующем примере кода импортируется пространство имен `INKEDLib` для объектов, указанных в библиотеке `Microsoft InkEdit Control 1.0`.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### Создание сборки взаимодействия при помощи программы Tlbimp  
  
1.  Введите расположение программы Tlbimp в путь поиска, если оно еще не задано как часть пути поиска и не в данный момент вы находитесь вне каталога, где она расположена.  
  
2.  Вызовите программу Tlbimp из командной строки, задав следующие данные:  
  
    -   Имя и размещение файла DLL, содержащего библиотеку типов  
  
    -   Имя и размещение пространства имен, в котором должна быть размещена информация  
  
    -   Имя и размещение нужной сборки взаимодействия  
  
     В коде ниже приведен пример:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Программу Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных объектов COM.  Тем не менее, объекты COM, на которые ссылаются через сборки взаимодействия, должны быть правильно зарегистрированы на том компьютере, где они будут использоваться.  Можно зарегистрировать объект COM при помощи программы Regsvr32, включенной в операционную систему Windows.  
  
## См. также  
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Пошаговое руководство. Реализация наследования с использованием COM\-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)