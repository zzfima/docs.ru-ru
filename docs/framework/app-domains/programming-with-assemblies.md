---
title: "Программирование с использованием сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 368021062a3ad49d2c63f92797c59b8c0f1cddfc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="programming-with-assemblies"></a>Программирование с использованием сборок
Сборки являются структурными элементами .NET Framework. Они составляют основную единицу развертывания, управления версиями, повторного использования, областей действия активации и разрешений безопасности. Сборка предоставляет среде CLR сведения, необходимые для распознавания реализаций типов. Она представляет собой коллекцию типов и ресурсов, собранных для совместной работы и образующих логическую функциональную единицу. Для среды выполнения тип не существует вне контекста сборки.  
  
 В этом разделе описываются процедуры создания модулей, сборок из модулей, пары ключей, а также подписывания сборки строгим именем и установки сборки в глобальный кэш сборок. Кроме того, в этом разделе описывается использование [дизассемблера MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для просмотра данных манифеста сборки.  
  
> [!NOTE]
>  Начиная с .NET Framework версии 2.0, среда выполнения не загружает сборку, которая была скомпилирована на платформе .NET Framework, номер версии которой выше номера версии текущей загруженной среды выполнения. Это применимо к сочетанию основного и дополнительного номеров для номера версии.  
  
## <a name="in-this-section"></a>Содержание  
 [Создание сборок](../../../docs/framework/app-domains/create-assemblies.md)  
 Содержит обзор однофайловых и многофайловых сборок.  
  
 [Имена сборок](../../../docs/framework/app-domains/assembly-names.md)  
 Общие сведения об именовании сборок.  
  
 [Практическое руководство. Определение полного имени сборки](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Описание определения полного имени сборки.  
  
 [Выполнение приложений интрасети с полным доверием](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Описание способа указания устаревшей политики безопасности для сборок с полным доверием в общем ресурсе интрасети.  
  
 [Расположение сборки](../../../docs/framework/app-domains/assembly-location.md)  
 Обзор мест размещения сборок.  
  
 [Практическое руководство. Построение однофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Описание способа создания однофайловой сборки.  
  
 [Многофайловые сборки](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Описание причин создания многофайловых сборок.  
  
 [Практическое руководство. Создание многофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Описание способа создания многофайловой сборки.  
  
 [Настройка атрибутов сборки](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Описание атрибутов сборки и способов их настройки.  
  
 [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Описание способа и причин подписи сборки строгим именем (с перечнем практических руководств).  
  
 [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Описывает, как отложить подписывание сборки.  
  
 [Работа со сборками и глобальным кэшем сборок](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Описание способа и причин добавления сборок в глобальный кэш сборок (с перечнем практических руководств).  
  
 [Практическое руководство. Просмотр содержимого сборок](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Описание использования дизассемблера MSIL (Ildasm.exe) для просмотра содержимого сборки.  
  
 [Переадресация типов в среде CLR](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Описание использования переадресации типов для перемещения типа в другую сборку, не нарушая работу существующих приложений.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Reflection.Assembly>  
 Класс .NET Framework, представляющий сборку.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Практическое руководство. Получение сведений о типах и членах из сборки](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Описание программного получения типа и других сведений из сборки.  
  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Общий обзор сборок среды CLR.  
  
 [Управление версиями сборок](../../../docs/framework/app-domains/assembly-versioning.md)  
 Общие сведения о привязке сборок и об атрибутах <xref:System.Reflection.AssemblyVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Описывается то, как среда выполнения определяет, какую сборку следует использовать для выполнения запроса привязки.  
  
 [Отражение](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Использование класса **Reflection** для получения сведений о сборке.

