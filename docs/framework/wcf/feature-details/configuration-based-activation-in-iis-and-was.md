---
title: "Активация на основе конфигурации в IIS и WAS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0938b98a3f079d03653df55f10c26a4a62db5bf3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuration-based-activation-in-iis-and-was"></a>Активация на основе конфигурации в IIS и WAS
Обычно при размещении службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в каталоге IIS или WAS следует предоставить SVC-файл. SVC-файл содержит имя службы, а также дополнительную пользовательскую фабрику узла службы. С помощью этого дополнительного файла добавляются служебные данные по управлению. Функция активации на основе конфигурации снимает требование по наличию SVC-файла и, следовательно, по наличию связанных служебных данных.  
  
## <a name="configuration-based-activation"></a>Активация на основе конфигурации  
 Активация на основе конфигурации принимает метаданные, которые используются для размещения в SVC-файле, и помещает их в файл Web.config. Внутри <`serviceHostingEnvironment`> отсутствует элемент <`serviceActivations`> элемент. Внутри <`serviceActivations`> элемент одного или нескольких <`add`> элементов, по одному для каждой размещенной службы. <`add`> Содержит атрибуты, которые позволяют задать относительный адрес для службы и тип службы или фабрики узла службы. В следующем примере конфигурации показано, каким образом используется этот раздел.  
  
> [!NOTE]
>  Каждый <`add`> элемента должно быть указано, службы или атрибут фабрики. Можно указать и атрибут службы, и атрибут фабрики.  
  
```xml  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 Такой код, показанный в файле Web.config, позволяет поместить исходный код службы в каталог App_Code приложения или откомпилированную сборку в каталог Bin приложения.  
  
> [!NOTE]
>  -   При использовании активации на основе конфигурации, встроенный программный код в SVC-файлах не поддерживается.  
> -   `relativeAddress` Атрибута должно быть присвоено относительный адрес. Например, «\<вложенный каталог > / service.svc» или «~ /\<подопераций/service.svc».  
> -   Если зарегистрирован относительный адрес, который не содержит известного расширения имени, связанного с WCF, то будет создано исключение конфигурации.  
> -   Относительный адрес указывается относительно корневого каталога виртуального приложения.  
> -   Поскольку модель конфигурации имеет иерархическую структуру, относительный адрес, который зарегистрирован на уровне компьютера и узла, наследуется виртуальными приложениями.  
> -   Регистрация в файле конфигурации имеет более высокий приоритет, чем параметры в SVC-файле, XAMLX-файле, XOML-файле и других файлах.  
> -   Все символы обратной косой черты «\» в URI, отправляемых в IIS/WAS, автоматически преобразуются в символы косой черты «/». Если добавляемый относительный адрес содержит символ «\», а в IIS отправлен URI, который использует относительный адрес, то символ обратной косой черты преобразуется в символ косой черты и IIS не может сопоставить его с относительным адресом. Службы IIS отправляют сведения трассировки, которые указывают, что соответствие не найдено.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>  
 [Размещение служб](../../../../docs/framework/wcf/hosting-services.md)  
 [Общие сведения о размещении служб рабочих процессов](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [\<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
