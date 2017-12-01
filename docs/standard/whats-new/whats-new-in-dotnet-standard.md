---
title: "Новые возможности .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>Новые возможности .NET Standard

.NET Standard имеет формальные спецификация, определяющая набор с версиями интерфейсы API, которые должны быть доступны в реализациях .NET, соответствующие этой версии стандарта. Решение .NET Standard ориентировано на разработчиков библиотек. Это библиотека, которая ссылается на версию .NET Standard можно использовать в любой реализации .NET Framework, .NET Core или Xamarin, совместимый с этой версией стандартной.

Самую последнюю версию .NET Standard является версия 2.0. Он включен с помощью пакета SDK .NET Core 2.0, а также с Visual Studio 2017 г. версия 15,3 с рабочей нагрузкой .NET Core установлен.

## <a name="supported-net-implementations"></a>Поддерживаемые реализаций .NET

Стандартная .NET 2.0 поддерживается следующими реализациями .NET:

- .NET core 2.0
- .NET Framework 4.6.1
- Моно 5.4.
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- Универсальная платформа Windows 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>Новые возможности .NET Standard 2.0
 
Стандартная .NET 2.0 включает следующие новые функции:

**Значительно расширенный набор интерфейсов API**

До версии 1.6 .NET Standard включены сравнительно небольшой набор API-интерфейсов. Среди тех исключен были многие API, которые часто использовались в .NET Framework или Xamarin. Это осложняет разработки, так как оно требует разработчикам искать подходящие замены для знакомы API при их разработке приложений и библиотек, предназначенных для нескольких реализаций .NET. Стандартная .NET 2.0 это ограничение адреса путем добавления до 20 000 интерфейсов API не были доступны в стандартных .NET версии 1.6, предыдущие версии стандарта. Список API, которые были добавлены к стандартной .NET 2.0 см. в разделе [vs .NET 2.0 стандартная 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Некоторые добавления к <xref:System> пространства имен в .NET 2.0 стандартная включают:

- Поддержка <xref:System.AppDomain> класса.
- Улучшенная поддержка работы с массивами из дополнительных членов в <xref:System.Array> класса.
- Улучшенная поддержка работа с атрибутами дополнительных членов в <xref:System.Attribute> класса.
- Лучше календарь поддержки и дополнительные параметры форматирования для <xref:System.DateTime> значения.
- Дополнительные <xref:System.Decimal> округления функциональные возможности.
- Дополнительные возможности в <xref:System.Environment> класса.
- Расширенный контроль над сборщик мусора через <xref:System.GC> класса.
- Улучшенная поддержка для сравнения строк, перечисления и нормализации в <xref:System.String> класса.
- Поддержка летнему корректировки и времени перехода в <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime> классы.
- Значительно улучшено функциональные возможности <xref:System.Type> класса.
- Улучшенная поддержка десериализации объектов исключений путем добавления к конструктору исключения с <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext> параметров.

**Поддержка библиотек .NET Framework**

Просто огромным большинство библиотек целевой платформы .NET Framework, а не .NET Standard. Однако большая часть вызовов в этих библиотек, API-интерфейсов, включенные в стандартный .NET 2.0. Начиная с .NET Standard 2.0, доступны библиотеки .NET Framework из .NET Standard библиотеки с помощью [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification). Этот уровень совместимости прозрачно для разработчиков; не нужно ничего делать, чтобы воспользоваться преимуществами библиотеки .NET Framework.

Один требуется, что API, вызываемые библиотекой классов .NET Framework должен быть включен в стандартных .NET 2.0.

**Поддержка Visual Basic**

Теперь можно разрабатывать .NET стандартных библиотек в Visual Basic. Разработчики Visual Basic, с помощью Visual Studio 2017 г. версия 15,3 или более поздней версии с рабочей нагрузкой .NET Core установлены Visual Studio теперь включает шаблон Стандартная библиотека классов .NET. Для разработчиков Visual Basic, которые используют другие средства разработки и среды, можно использовать [dotnet новый](../../core/tools/dotnet-new.md) команду, чтобы создать проект стандартной библиотеки .NET. Дополнительные сведения см. в разделе [средства поддержки для библиотек .NET Standard](#tooling).

<a name="tooling" />**Поддержка инструментами .NET стандартные библиотеки**

С выпуском ядра .NET 2.0 и .NET 2.0 Standard, как Visual Studio 2017 г. и [.NET Core интерфейс командной строки (CLI)](../../core/tools/index.md) включает инструменты для создания библиотеки .NET Standard. 

При установке Visual Studio с **кросс платформенной разработки .NET Core** рабочей нагрузки, можно создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на следующем рисунке. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Добавьте новый .NET Standard проект библиотеки](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Добавьте новый .NET Standard проект библиотеки](./media/std-project-vb.png)
---

Если вы используете .NET Core (CLI), следующие [dotnet новый](../../core/tools/dotnet-new.md) команда создает проект библиотеки классов, ориентированном на .NET Standard 2.0.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>См. также
[.NET standard](../net-standard.md)
[введение .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
