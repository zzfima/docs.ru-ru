---
title: <add> из <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 929773fcb6b6a3ee5c75aa970147277d9dbe7b45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920028"
---
# <a name="add-of-serviceactivations"></a>\<Добавление > \<> serviceActivations

Элемент конфигурации, позволяющий определить параметры активации виртуальной службы, которые сопоставляются с типами служб Windows Communication Foundation (WCF). Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.

\<системой. ServiceModel > \
\<serviceHostingEnvironment >

## <a name="syntax"></a>Синтаксис

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|фабрика|Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.|
|служба|ServiceType, реализующий службу (либо полное, либо короткое имя типа) (когда оно размещено в папке App_Code).|
|relativeAddress|Относительный адрес в текущем приложении IIS (например, «Service.svc»). В WCF 4.0 этот относительный адрес должен содержать одно из известных расширений файлов (SVC, XAMLX и т. д.). Ни один физический файл не должен существовать по адресу relativeUrl|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<serviceHostingEnvironment >](servicehostingenvironment.md)|Раздел конфигурации, в котором описываются параметры активации.|

## <a name="remarks"></a>Примечания

В следующем примере показано, как настроить параметры активации в файле web.config.

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.

Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения. Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения. Кроме того, `serviceHostingEnvironment` является machineToApplication наследуемым разделом. Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.

Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP. Для этого требуются расширения в Релативеаддресс, например. svc,. XOML или. xamlx. Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение. При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
