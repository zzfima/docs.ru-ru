---
title: "Marshaling Data with COM Interop | Microsoft Docs"
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
  - "COM interop, data marshaling"
  - "marshaling data, COM interop"
ms.assetid: 0bcdd7bf-5026-43eb-b08b-f03f90db9df9
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Marshaling Data with COM Interop
COM\-взаимодействие обеспечивает поддержку как для использования COM\-объектов из управляемого кода, так и для предоставления доступа к управляемым объектам для COM.  Поддержка маршалинга данных в COM и обратно достаточно полная и почти всегда обеспечивает правильное поведение маршалинга.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] включает следующие средства COM\-взаимодействия:  
  
-   [Средство импорта библиотек типов \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), преобразующее библиотеку типов COM в сборку взаимодействия.  Эта сборка используется службой маршалинга взаимодействия для создания оболочек, маршалирующих данные между управляемой и неуправляемой памятью.  
  
-   [Средство экспорта библиотек типов \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), создающее из сборки библиотеку типов COM и формирующее оболочку, которая выполняет маршалинг при вызовах метода.  
  
 В этом разделе описаны процессы настройки оболочек взаимодействий для случаев, когда можно \(или необходимо\) предоставить упаковщику дополнительную информацию о типах.  
  
## В этом подразделе  
 [Типы данных COM](http://msdn.microsoft.com/ru-ru/f93ae35d-a416-4218-8700-c8218cc90061)  
 Содержит описание соответствующих управляемых и неуправляемых типов данных.  
  
 [Настройка вызываемых оболочек COM](http://msdn.microsoft.com/ru-ru/825177d3-4b2c-4723-82be-ce6ca2c34ace)  
 Описывается способ явного маршалинга типов данных с использованием атрибута **MarshalAsAttribute** во время разработки.  
  
 [Настройка вызываемых оболочек времени выполнения](http://msdn.microsoft.com/ru-ru/4652beaf-77d0-4f37-9687-ca193288c0be)  
 Описаны способы настройки связанного с маршалингом поведения типов в сборке взаимодействия и определения типов COM вручную.  
  
 [Практическое руководство. Миграция DCOM с управляемым кодов в WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Описывается перенос управляемого кода DCOM в WCF для получения наиболее безопасного решения.  
  
## Связанные подразделы  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ru-ru/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Приводятся ссылки на дополнительные сведения о включении COM\-компонентов в разрабатываемое приложение .NET Framework.  
  
 [Assembly to Type Library Conversion Summary](http://msdn.microsoft.com/ru-ru/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 Описывается процесс преобразования при экспорте сборки в библиотеку типов.  
  
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/ru-ru/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 Описывается процесс преобразования при экспорте библиотеки типов в сборку.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/ru-ru/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Описываются действия, поддерживаемые при использовании универсальных типов для COM\-взаимодействия.