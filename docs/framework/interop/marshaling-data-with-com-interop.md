---
title: "Маршалинг с помощью COM- взаимодействия"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2def27790a1727bda524b8c14a93f7b78127a569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-com-interop"></a>Маршалинг с помощью COM- взаимодействия
COM-взаимодействие обеспечивает поддержку как для использования COM-объектов из управляемого кода, так и для предоставления доступа к управляемым объектам для COM. Поддержка маршалинга данных в COM и обратно достаточно полная и почти всегда обеспечивает правильное поведение маршалинга.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] включает следующие средства COM-взаимодействия:  
  
-   [Средство импорта библиотек типов (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), которое преобразует библиотеку типов COM в сборку взаимодействия. Эта сборка используется службой маршалинга взаимодействия для создания оболочек, маршалирующих данные между управляемой и неуправляемой памятью.  
  
-   [Средство экспорта библиотек типов (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), которое создает библиотеку типов COM из сборки и формирует оболочку, которая выполняет маршалинг при вызовах методов.  
  
 В следующих подразделах ссылки на разделы, описывающие процессы настройки оболочек взаимодействий для когда можно (или необходимо предоставить упаковщику дополнительную информацию о типах.  
  
## <a name="in-this-section"></a>Содержание  
[Как: создание оболочек вручную](how-to-create-wrappers-manually.md)   
Описывает, как вручную создать оболочку COM в управляемом исходном коде. 
 
 [Практическое руководство. Миграция DCOM с управляемым кодом в WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 В этой статье описывается перенос управляемого кода DCOM в WCF для получения наиболее безопасного решения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы данных COM](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)  
 Содержит описание соответствующих управляемых и неуправляемых типов данных.  
  
 [Настройка вызываемых оболочек COM](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)  
 Описывает способ явного маршалинга типов данных с использованием <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибута во время разработки.  
  
 [Настройка вызываемых оболочек времени выполнения](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)  
 Описаны способы настройки связанного с маршалингом поведения типов в сборке взаимодействия и определения типов COM вручную.  
  
 [Расширенное COM-взаимодействие](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)  
 Приводятся ссылки на дополнительные сведения о включении COM-компонентов в разрабатываемое приложение .NET Framework.  
  
 [Общие сведения о преобразовании сборки в библиотеку типов](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)  
 Описывается процесс преобразования при экспорте сборки в библиотеку типов.  
  
 [Общие сведения о преобразовании библиотеки типов в сборку](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)  
 Описывается процесс преобразования при экспорте библиотеки типов в сборку.  
  
 [Взаимодействие с помощью универсальных типов](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)  
 Описываются действия, поддерживаемые при использовании универсальных типов для взаимодействия COM.
