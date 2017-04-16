---
title: "Изменения среды выполнения в .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Изменения среды выполнения в .NET Framework 4.6
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в более поздней версии среды выполнения .NET Framework. Они также включают различия в поведении между приложениями, которые выполняются в разных средах .NET Framework. Они включают изменения в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [Сетевое взаимодействие](#Networking)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [Установка и развертывание](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Новый 64\-разрядный JIT\-компилятор](#RyuJIT)  
  
<a name="Core"></a>   
## Ядро  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|Начиная с [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] класс <xref:System.Globalization.PersianCalendar> использует алгоритм солнечного календаря Хиджры.|Этот алгоритм получает результаты, идентичные персидскому календарю, который в настоящее время используется в Иране и Афганистане. Он также выдает результаты, которые совпадают с предыдущим алгоритмом для дат с 1800 по 2023 гг. по григорианскому календарю. Даты вне этого диапазона могут отличаться, если класс <xref:System.Globalization.PersianCalendar> используется для преобразований дат \(например, между значениями даты по григорианскому календарю и датами в персидском календаре\) или для определения високосного года.<br /><br /> В результате изменений значение свойства <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> было изменено с 21 марта 0622 на 22 марта 0622 для систем, в которых установлена версия [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].<br /><br /> Дополнительные сведения см. в разделе <xref:System.Globalization.PersianCalendar>.|Дополнительный номер|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|Для домена приложения по умолчанию значение свойства <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> является производным от  <xref:System.Runtime.Versioning.TargetFrameworkAttribute>, если оно задано, за исключением случаев, когда оно явно определено путем назначения имени свойству <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.  В предыдущих версиях .NET Framework значение атрибута <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> — `null`, кроме случаев, когда выполняется несколько путей специального кода или создается домен не по умолчанию без явного указания   целевой платформы в свойстве <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.<br /><br /> Для доменов не по умолчанию отсутствуют изменения в способе определения значения свойства <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>. Если свойству <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> не задается явное значение, домен приложения не по умолчанию наследует имя целевой платформы из домена приложений по умолчанию.|Для домена приложений по умолчанию <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> может вернуть ненулевое значение, если оно ранее возвращало `null`. Это желаемое поведение.|Пограничный случай|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|Если платформой .NET Framework не поддерживается ни один из сертификатов, установленных в системе, при передаче значения `True` для аргумента `verbose` возвращается допустимая строка. В предыдущих версиях .NET Framework при попытке доступа к информации об открытом ключе для неподдерживаемых сертификатов иногда возникало исключение.|Этот метод является только информационным; в документации отмечено, что выходные данных могут быть не согласованы между версиями .NET Framework. Это значение влияет только на приложения, которые вызывают метод `ToString(True)` и установили сертификаты, не поддерживаемые .NET Framework. Это изменение обеспечивает надежность метода, возвращая строку, а не вызывая исключение.|Пограничный случай|  
|Отражение и распределенная модель COM \(DCOM\)|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затрагиваются следующие типы: <xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> и его производные типы, включая <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> и <xref:System.Reflection.TypeInfo>; <xref:System.Reflection.MethodBody>; <xref:System.Reflection.Module>; <xref:System.Reflection.ParameterInfo>.|Вызовы [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) для возврата объекта `E_NOINTERFACE`.|Дополнительный номер|  
  
<a name="Networking"></a>   
## Сетевое взаимодействие  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Значения даты и времени в классе <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>.|Чтобы обеспечить соответствие требованиям [RFC822](http://www.ietf.org/rfc/rfc0822.txt) и [RFC2822](http://www.ietf.org/rfc/rfc2822.txt), форматированное значение даты и времени теперь имеет двузначные часы. Ранее значения часа до 10:00 указывались одной цифрой.|Это изменение влияет на следующие сценарии использования:<br /><br /> -   Сравнение длин или хэш\-кодов сериализованных объектов <xref:System.Net.Mime.ContentDisposition> в версиях .NET Framework.<br />-   Сравнение возвращаемого значения представления метода или строки <xref:System.Net.Mime.ContentDisposition.ToString%2A> значений свойств даты и времени <xref:System.Net.Mime.ContentDisposition> в версиях .NET Framework.|Дополнительный номер|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Отрисовка окон при использовании нескольких мониторов|Все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.|См. раздел [Уменьшение. Отрисовка окна WPF](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md).|Дополнительный номер|  
|Проверка орфографии в элементах управления WPF с поддержкой текста|При работе в Windows 10 функция проверки орфографии может не работать, поскольку возможности проверки орфографии платформы доступны только для языков из списка языков ввода.|В Windows 10 при добавлении языка в список доступных клавиатур Windows автоматически загружает и устанавливает соответствующий пакет компонента по запросу \(FOD\), который предоставляет возможности проверки орфографии. При добавлении языка в список языков ввода проверка орфографии будет поддерживаться.|Дополнительный номер|  
  
<a name="Setup"></a>   
## Установка и развертывание  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Управление версиями продукта|Управление версиями продукта отличается от предыдущих версий платформы .NET Framework \(.NET Framework 4, 4.5, 4.5.1 и 4.5.2\). Для получения дополнительной информации см. [Уменьшение: управление версиями продукта](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|См. раздел [Уменьшение: управление версиями продукта](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Средний|  
  
<a name="ClickOnce"></a>   
## ClickOnce  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Приложения опубликованы с помощью ClickOnce с использованием сертификата подписи кода SHA\-256.|Приложения ClickOnce на платформе [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] или более ранних версий, подписанные с помощью сертификата SHA\-256, больше не имеют зависимостей среды выполнения от [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии.|Ранее подписывание приложения ClickOnce, предназначенного для [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] или более ранних версий с помощью сертификата SHA\-256, требовало установки [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии на целевой системе. Это приводило к ошибкам в случае ее отсутствия. Это изменение удаляет зависимость и позволяет использовать сертификаты SHA\-256 для подписи приложений ClickOnce на платформе [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] и более ранних версий.|Дополнительный номер|  
  
<a name="RyuJIT"></a>   
## Новый 64\-разрядный JIT\-компилятор  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Обработка исключения \(возврат из региона `try`\)|В отличие от старого JIT\-компилятора JIT64, новый 64\-разрядный JIT\-компилятор не разрешает инструкцию IL [ret](http://msdn.microsoft.com/library/system.reflection.emit.opcodes.ret.aspx) в области `try`.|Возврат из региона `try` запрещен в спецификации ECMA\-335, и ни один известный управляемый компилятор не создает такие IL. Однако компилятор JIT64 выполнит такие IL, если они созданы с помощью порождения отражения.|Пограничный случай|