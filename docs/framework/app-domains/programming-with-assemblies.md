---
title: "Программирование с использованием сборок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сборки [платформа .NET Framework], программирование"
  - "программирование сборок"
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Программирование с использованием сборок
Сборки являются стандартными блоками приложений платформы .NET Framework; они составляют основную единицу развертывания, управления версиями, многократного использования, областей действия активации и разрешений безопасности.  Сборка предоставляет среде CLR сведения, необходимые для распознавания реализаций типов.  Сборка представляет собой коллекцию типов и ресурсов, собранных для совместной работы и формирующих функциональную логическую единицу.  Для среды выполнения тип не существует вне контекста сборки.  
  
 В этом разделе описывается способ создания модулей, сборок из модулей, способ создания пары ключей и подписи сборок строгим именем, а также способ установки сборки в глобальный кэш сборок.  Кроме того, в этом разделе описывается способ использования средства [MSIL Disassembler \(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для просмотра данных манифеста сборки.  
  
> [!NOTE]
>  Начиная с платформы .NET Framework версии 2.0, среда выполнения не загружает сборки, которые были скомпилированы версиями платформы .NET Framework, чей номер версии выше, чем у текущей среды выполнения.  Это относится к сочетанию основных и дополнительных номеров версии.  
  
## В этом подразделе  
 [Создание сборок](../../../docs/framework/app-domains/create-assemblies.md)  
 Предоставляет основные сведения об однофайловых и многофайловых сборках.  
  
 [Имена сборок](../../../docs/framework/app-domains/assembly-names.md)  
 Предоставляет основные сведения о назначении имени для сборки.  
  
 [Практическое руководство. Определение полного имени сборки](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Описывает способы определения полного имени сборки.  
  
 [Выполнение приложений интранета с полным доверием](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Описывает способы указания существующей политики безопасности для сборок с полным доверием в общем ресурсе интранета.  
  
 [Расположение сборки](../../../docs/framework/app-domains/assembly-location.md)  
 Предоставляет основные сведения о расположении сборок.  
  
 [Практическое руководство. Построение однофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Описывает способ создания однофайловой сборки.  
  
 [Многофайловые сборки](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Описывает ситуации, в которых необходимо создание многофайловых сборок.  
  
 [Практическое руководство. Создание многофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Описывает способ создания многофайловой сборки.  
  
 [Настройка атрибутов сборки](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Описывает атрибуты сборки и способы их настройки.  
  
 [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Описывает способы и причины подписи сборок строгими именами, включает практические руководства.  
  
 [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Описывает способ выполнения отложенной подписи сборки.  
  
 [Работа со сборками и глобальным кэшем сборок](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Описывает способ и причины добавления сборок в глобальный кэш сборок, включает практические руководства.  
  
 [Практическое руководство. Просмотр содержимого сборок](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Описывает использование средства MSIL Disassembler \(Ildasm.exe\) для просмотра содержимого сборки.  
  
 [Переадресация типов в общеязыковой среде CLR](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Описывает способы использования пересылки типов для перемещения типа в другую сборку, не нарушая работу существующих приложений.  
  
## Ссылка  
 <xref:System.Reflection.Assembly>  
 Класс платформы .NET Framework, представляющий сборку.  
  
## Связанные подразделы  
 [Практическое руководство. Получение сведений о типах и членах из сборки](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Описывает способ программного извлечения из сборки сведений о типе и других данных.  
  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Общие сведения о сборках среды CLR.  
  
 [Управление версиями сборок](../../../docs/framework/app-domains/assembly-versioning.md)  
 Общие сведения о привязке сборок и атрибутов <xref:System.Reflection.AssemblyVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Описывает способ определения средой выполнения сборки, используемой для разрешения запроса привязки.  
  
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Использование класса **Отражение** для получения сведений о сборке.