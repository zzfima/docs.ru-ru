---
title: "Маршалинг с помощью COM- взаимодействия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.assetid: 0bcdd7bf-5026-43eb-b08b-f03f90db9df9
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7e798f41f7c770fb0db0abf4a07e53cbaa6ccb40
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-data-with-com-interop"></a>Маршалинг с помощью COM- взаимодействия
COM-взаимодействие обеспечивает поддержку как для использования COM-объектов из управляемого кода, так и для предоставления доступа к управляемым объектам для COM. Поддержка маршалинга данных в COM и обратно достаточно полная и почти всегда обеспечивает правильное поведение маршалинга.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] включает следующие средства COM-взаимодействия:  
  
-   [Средство импорта библиотек типов (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), которое преобразует библиотеку типов COM в сборку взаимодействия. Эта сборка используется службой маршалинга взаимодействия для создания оболочек, маршалирующих данные между управляемой и неуправляемой памятью.  
  
-   [Средство экспорта библиотек типов (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), которое создает библиотеку типов COM из сборки и формирует оболочку, которая выполняет маршалинг при вызовах методов.  
  
 В этом разделе описаны процессы настройки оболочек взаимодействий для случаев, когда можно (или необходимо) предоставить упаковщику дополнительную информацию о типах.  
  
## <a name="in-this-section"></a>Содержание  
 [Типы данных COM](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 Содержит описание соответствующих управляемых и неуправляемых типов данных.  
  
 [Настройка вызываемых оболочек COM](http://msdn.microsoft.com/en-us/825177d3-4b2c-4723-82be-ce6ca2c34ace)  
 В этой статье описан способ явного маршалинга типов данных с использованием атрибута **MarshalAsAttribute** во время разработки.  
  
 [Настройка вызываемых оболочек времени выполнения](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 Описаны способы настройки связанного с маршалингом поведения типов в сборке взаимодействия и определения типов COM вручную.  
  
 [Практическое руководство. Миграция DCOM с управляемым кодом в WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Описывается перенос управляемого кода DCOM в WCF для получения наиболее безопасного решения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Расширенное COM-взаимодействие](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Приводятся ссылки на дополнительные сведения о включении COM-компонентов в разрабатываемое приложение .NET Framework.  
  
 [Общие сведения о преобразовании сборки в библиотеку типов](http://msdn.microsoft.com/en-us/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 Описывается процесс преобразования при экспорте сборки в библиотеку типов.  
  
 [Общие сведения о преобразовании библиотеки типов в сборку](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 Описывается процесс преобразования при экспорте библиотеки типов в сборку.  
  
 [Взаимодействие с помощью универсальных типов](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Описываются действия, поддерживаемые при использовании универсальных типов для взаимодействия COM.

