---
title: "Компиляция приложений с помощью машинного кода .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 76645ae43ce6754ffdf505729ec1198785a71561
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="compiling-apps-with-net-native"></a>Компиляция приложений с помощью машинного кода .NET
[!INCLUDE[net_native](../../../includes/net-native-md.md)] — это технология предварительной компиляции, предназначенная для создания и развертывания приложений Windows, которая входит в состав [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]. Она автоматически компилирует окончательные версии приложений, написанных в форме управляемого кода (C# или Visual Basic) и предназначенных для .NET Framework и Windows 10, в машинный код.  
  
 Как правило приложения, предназначенные для платформа.NET Framework компилируются в промежуточный язык (IL). Во время выполнения JIT-компилятор преобразует инструкции IL в машинный код. В отличие от этого [!INCLUDE[net_native](../../../includes/net-native-md.md)] компилирует приложения Windows непосредственно в машинный код. Для разработчиков это означает:  
  
-   Обеспечивается высокая производительность машинного кода приложений.  
  
-   Можно продолжить программировать в C# или Visual Basic.  
  
-   Можно продолжать использовать преимущества ресурсов платформы .NET Framework, включая библиотеки классов, сбор мусора, автоматическое управление памяти и обработку исключений.  
  
 Для пользователей приложений [!INCLUDE[net_native](../../../includes/net-native-md.md)] обеспечивает следующие преимущества:  
  
-   Быстрое время выполнения  
  
-   Постоянно быстрое время запуска  
  
-   Низкая стоимость развертывания и обновления  
  
-   Оптимизированное использование памяти приложением  
  
 Но [!INCLUDE[net_native](../../../includes/net-native-md.md)] не ограничивается только компиляцией в машинный код. Он преобразует способ построения и выполнения приложений на платформе .NET Framework. В частности:  
  
-   Во время предварительной компиляции необходимые части платформы .NET Framework статически связываются с приложением. Это позволяет приложению работать с библиотеками локальных приложений платформы.NET Framework, а компилятору — выполнять глобальный анализ для улучшения производительности. В результате приложения постоянно запускаются быстрее даже после обновлений платформы .NET Framework.  
  
-   Среда выполнения [!INCLUDE[net_native](../../../includes/net-native-md.md)] оптимизирована для статической предварительной компиляции и, таким образом, способна обеспечить высокую производительность. В то же время она сохраняет основные функции отражения, которые разработчики считают такими полезными.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] использует то же сервер, что и компилятор C++, который оптимизирован для статических сценариев предварительной компиляции.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] способна обеспечить повышение производительности для C++ разработчиков управляемого кода, так как она использует такие же или аналогичные средства, что и C++ за кулисами, как показано в следующей таблице.  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|C++|  
|-|----------------------------------------------------------------|-----------|  
|Библиотеки|Платформа.NET Framework + среда выполнения Windows|Win32 + среда выполнения Windows|  
|Компилятор|Оптимизирующий компилятор UTC|Оптимизирующий компилятор UTC|  
|Развернут|Готов к запуску двоичных файлов|Готов к запуску двоичных файлов (ASM)|  
|Среда выполнения|MRT.dll (минимальной среды CLR)|CRT.dll (среда выполнения C)|  
  
 Для приложений, предназначенных для Windows 10, выполняется передача двоичных файлов компиляции машинного кода .NET в пакетах приложений (файлы APPX) в Магазин Windows.  
  
## <a name="in-this-section"></a>Содержание  
 Дополнительные сведения о разработке приложений при использовании компиляции машинного кода .NET см. в следующих разделах  
  
-   [Приступая к компиляции кода с помощью машинного кода .NET: пошаговое руководство разработчика](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   [Машинный код .NET и компиляция](../../../docs/framework/net-native/net-native-and-compilation.md) — как проект компилируется в машинный код .NET.  
  
-   [Отражение и .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [API-интерфейсы, основанные на отражении](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [Справочник по API отражения](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Сериализация и метаданные](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [Миграция приложения для Магазина Windows в .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [.NET Native. Устранение общих неполадок](../../../docs/framework/net-native/net-native-general-troubleshooting.md)  
  
## <a name="see-also"></a>См. также  
 [Вопросы и ответы по .NET Native](http://msdn.microsoft.com/vstudio/dn642499.aspx)

