---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: fb7c699612ef12aae39aaeadaf170d0e8f2553cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936448"
---
# <a name="serviceactivations"></a>\<serviceActivations >

Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, сопоставленные с типами служб Windows Communication Foundation (WCF). Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.

\<системой. ServiceModel > \
\<serviceHostingEnvironment > \
\<serviceActivations >

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

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|Добавляет элемент конфигурации, который задает активацию приложения службы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<serviceHostingEnvironment >](servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|

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

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
