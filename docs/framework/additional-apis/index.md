---
title: "Дополнительные библиотеки классов и интерфейсы API | Документы Майкрософт"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: ru-ru
ms.lasthandoff: 05/02/2017

---

# <a name="additional-class-libraries-and-apis"></a>Дополнительные библиотеки классов и интерфейсы API

Платформа .NET Framework постоянно развивается. С целью совершенствования кроссплатформенной разработки и оперативного предоставления новых функциональных возможностей нашим клиентам мы выпускаем новые возможности в виде внештатных выпусков. В этом разделе перечислены внештатные проекты, для которых мы предоставляем документацию.  
  
Кроме того, некоторые библиотеки предназначены для конкретных платформ или реализаций .NET Framework. Например, благодаря классу <xref:System.Text.CodePagesEncodingProvider> кодировки кодовых страниц становятся доступными для приложений UWP, разработанных с помощью .NET Framework. В этой статье эти библиотеки перечислены тоже.  
  
## <a name="oob-projects"></a>Встроенные проекты
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется. |
| <xref:System.Net.Http.WinHttpHandler> | Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows. |
| [System.Numerics.Vectors](https://msdn.microsoft.com/library/mt452176.aspx) | Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма. |  

## <a name="platform-specific-libraries"></a>Библиотеки для конкретных платформ
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Расширяет класс <xref:System.Text.EncodingProvider>, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальной платформы Windows. |  
  
## <a name="private-apis"></a>Частные интерфейсы API  

Эти API-интерфейсы используются для поддержки инфраструктуры продукта и не предназначены для использования непосредственно в коде.  
  
| Имя API |  
| -------- |  
| [s_isDebuggerCheckDisabledForTestPurposes Field](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [Класс DataMemberFieldEditor](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [Класс DataMemberListEditor](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a>См. также

[.NET Framework и отдельные выпуски](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

