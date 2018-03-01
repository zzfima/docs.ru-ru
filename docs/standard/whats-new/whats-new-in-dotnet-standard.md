---
title: "Новые возможности .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a>Новые возможности .NET Standard

.NET Standard — это формальная спецификация, определяющая ряд версий с набором интерфейсов API, которые должны быть доступны во всех реализациях .NET, соответствующих определенной версии стандарта. Решение .NET Standard ориентировано на разработчиков библиотек. Библиотека, которая предназначена для некоторой версии .NET Standard, может использоваться в любой реализации .NET Framework, .NET Core или Xamarin, совместимой с той же версией стандарта.

Сейчас последней версией является .NET Standard 2.0. Она входит в пакет SDK для .NET Core 2.0, а также в Visual Studio 2017 версии 15.3 при установке с рабочей нагрузкой .NET Core.

## <a name="supported-net-implementations"></a>Поддерживаемые реализации .NET

.NET Standard 2.0 поддерживается следующими реализациями .NET:

- .NET Core 2.0;
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0;
- универсальная платформа Windows 10.0.16299.

## <a name="whats-new-in-the-net-standard-20"></a>Новые возможности .NET Standard 2.0
 
.NET Standard 2.0 содержит следующие новые функции и компоненты.

**Значительно расширенный набор интерфейсов API**

Вплоть до версии 1.6 спецификация .NET Standard содержала сравнительно небольшой набор API-интерфейсов. Среди прочего, в их числе не было многих API, которые часто используются на платформах .NET Framework и Xamarin. Это усложняет разработку, так как разработчикам приходится искать подходящие средства для замены знакомых API при разработке приложений и библиотек для нескольких реализаций .NET. В .NET Standard 2.0 это ограничение устранено: в стандарт добавлены более 20 000 интерфейсов API, недоступных в предыдущей версии .NET Standard 1.6. Список интерфейсов API, добавленных в .NET Standard 2.0 см. в [документе сравнения возможностей .NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Вот лишь некоторые возможности, добавленные в пространство имен <xref:System> .NET Standard 2.0:

- поддержка класса <xref:System.AppDomain>;
- улучшенная поддержка работы с массивами из дополнительных элементов класса <xref:System.Array>;
- улучшенная поддержка работы с атрибутами из дополнительных элементов класса <xref:System.Attribute>;
- улучшенная поддержка календаря и дополнительных параметров форматирования для значений <xref:System.DateTime>;
- дополнительные возможности округления <xref:System.Decimal>;
- дополнительные функциональные возможности для класса <xref:System.Environment>;
- расширенный контроль над сборщиком мусора через класс <xref:System.GC>;
- улучшенная поддержка сравнения строк, перечисления и нормализации в классе <xref:System.String>;
- поддержка перехода на летнее время в классах <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime>;
- значительно улучшенная функциональность класса <xref:System.Type>;
- улучшенная поддержка десериализации объектов исключений благодаря новому конструктору исключений с параметрами <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext>.

**Поддержка библиотек .NET Framework**

Практически все библиотеки предназначены для .NET Framework, а не .NET Standard. Но при этом большая часть вызовов в этих библиотеках направлена к интерфейсам API .NET Standard 2.0. Начиная с .NET Standard 2.0 библиотеки .NET Framework доступны из библиотек .NET Standard через [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification). Этот уровень совместимости прозрачен для разработчиков, то есть от них не требуется никаких действий, чтобы пользоваться библиотеками .NET Framework.

Действует только одно требование: API, вызываемые библиотекой классов .NET Framework, должны быть включены в .NET Standard 2.0.

**Поддержка Visual Basic**

Теперь вы можете разрабатывать библиотеки .NET Standard на Visual Basic. Разработчики Visual Basic, использующие Visual Studio 2017 версии 15.3 или более поздней версии с установленной рабочей нагрузкой .NET Core, теперь получают в Visual Studio шаблон библиотеки классов .NET Standard. Разработчики Visual Basic, которые используют другие средства и среды разработки, могут создать проект библиотеки .NET Standard с помощью команды [dotnet new](../../core/tools/dotnet-new.md). Дополнительные сведения см. в разделе [Поддержка средств для библиотек .NET Standard](#tooling).

<a name="tooling" />**Поддержка средств для библиотек .NET Standard**

С момента выхода .NET Core 2.0 и .NET Standard 2.0 поддержка средств для создания библиотек .NET Standard включена в Visual Studio 2017 и в [.NET Core CLI](../../core/tools/index.md). 

Если у вас установлен Visual Studio с рабочей нагрузкой **для кроссплатформенной разработки .NET Core**, вы можете создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на следующем рисунке. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Добавление нового проекта библиотеки .NET Standard](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Добавление нового проекта библиотеки .NET Standard](./media/std-project-vb.png)
---

Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>См. также
[.NET Standard](../net-standard.md)
[Объявление о выпуске .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
