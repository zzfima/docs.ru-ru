---
title: "Даты, время и часовые пояса | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 2445188fda029ddc0f673d4c81f99f7f46edb89b
ms.lasthandoff: 04/08/2017

---
# <a name="dates-times-and-time-zones"></a>Даты, время и часовые пояса
В дополнение к основной структуре <xref:System.DateTime> платформа [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] предоставляет следующие классы, которые поддерживают работу с часовыми поясами:  
  
-   <xref:System.TimeZone>  
  
     Этот класс используется для работы с локальным часовым поясом и с временем в формате UTC.  Большинство функциональных возможностей класса <xref:System.TimeZone> перенесены в класс <xref:System.TimeZoneInfo>.  
  
-   <xref:System.TimeZoneInfo>  
  
     Этот класс используется для работы с любым часовым поясом, который является стандартным в системе, для создания новых часовых поясов и для быстрого преобразования значений даты и времени из одного часового пояса в другой. Для новых разработок вместо класса <xref:System.TimeZone> используйте класс <xref:System.TimeZoneInfo>.  
  
-   <xref:System.DateTimeOffset>  
  
     Эта структура используется для работы с датами и временем, чье смещение (или различие) от времени в формате UTC известно. Структура <xref:System.DateTimeOffset> объединяет значение даты и времени со смещением этого времени относительно времени в формате UTC. Благодаря связи со временем в формате UTC отдельное значение даты и времени однозначно идентифицирует единственный момент времени. Это делает значение <xref:System.DateTimeOffset> более пригодным для переноса с одного компьютера на другой, чем значение <xref:System.DateTime>.  
  
 Этот раздел документации содержит сведения, необходимые для работы с часовыми поясами и создания приложений, поддерживающих часовые пояса и способных преобразовывать дату и время из одного часового пояса в другой.  
  
## <a name="in-this-section"></a>Содержание  
 [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md).  
 Статья содержит описание терминологии, основных понятий и вопросов, связанных с созданием приложений, использующих часовые пояса.  
  
 [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).  
 Из этой статьи вы узнаете, когда использовать типы <xref:System.DateTime>, <xref:System.DateTimeOffset> и <xref:System.TimeZoneInfo> при работе с данными времени и даты.  
  
 [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).  
 Статья содержит способы перечисления часовых поясов, найденных на локальном компьютере.  
  
 [Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](../../../docs/standard/datetime/enumerate-time-zones.md).  
 Статья содержит примеры, в которых перечисляются часовые пояса, определенные в реестре компьютера, а пользователям предоставляется возможность выбрать предопределенный часовой пояс из списка.  
  
 [Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](../../../docs/standard/datetime/access-utc-and-local.md).  
 Из этой статьи вы узнаете, как использовать местный часовой пояс и часовые пояса UTC.  
  
 [Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
 В этой статье описываются способы создания экземпляра объекта <xref:System.TimeZoneInfo> из локального системного реестра.  
  
 [Создание экземпляра объекта DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md).  
 Статья содержит писание способов, с помощью которых можно создать экземпляр объекта <xref:System.DateTimeOffset> и преобразовать значение <xref:System.DateTime> в значение <xref:System.DateTimeOffset>.  
  
 [Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).  
 В статье описываются способы создания пользовательского часового пояса, который не поддерживает переход летнее время и с него.  
  
 [Практическое руководство. Создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
 В статье описываются способы создания пользовательского часового пояса, который поддерживает как минимум один переход летнее время и с него.  
  
 [Сохранение и восстановление часовых поясов](../../../docs/standard/datetime/saving-and-restoring-time-zones.md).  
 В статье описываются сериализация и десериализация данных часового пояса в <xref:System.TimeZoneInfo> и демонстрируются некоторые сценарии, в которых могут использоваться эти функции.  
  
 [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).  
 Из этой статьи вы узнаете, как создавать пользовательские часовые пояса и сохранять их информацию в файле ресурсов.  
  
 [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
 Из этой статьи вы узнаете, как создать экземпляр пользовательского часового пояса, который сохранен во внедренном файле ресурсов.  
  
 [Выполнение арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md).  
 Статья содержит обзор вопросов, связанных со сложением, вычитанием и сравнением значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.  
  
 [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).  
 Из этой статьи вы узнаете, как выполнять арифметические операции с датами и временем, отражающие правила коррекции часовых поясов.  
  
 [Взаимное преобразование структур DateTime и DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md).  
 Из этой статьи вы узнаете, как преобразовывать значения <xref:System.DateTime> в значения <xref:System.DateTimeOffset> и наоборот.  
  
 [Преобразование времени из одного часового пояса в другой](../../../docs/standard/datetime/converting-between-time-zones.md).  
 Из этой статьи вы узнаете, как преобразовывать время из одного часового пояса в другой.  
  
 [Практическое руководство. Разрешение проблемы неоднозначности времени](../../../docs/standard/datetime/resolve-ambiguous-times.md).  
 Статья содержит сведения об устранении неоднозначного времени с помощью его сопоставления с часовым поясом стандартного времени.  
  
 [Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md).  
 Статья содержит сведения о том, как разрешить пользователям определять сопоставление между неоднозначными местным временем и временем в формате UTC.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.TimeZoneInfo?displayProperty=fullName>
