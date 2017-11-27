---
title: "Развертывание службы WCF, размещенной в IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
caps.latest.revision: "30"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42c30c5f83f8245531a357c2d0b179deb87a2845
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Развертывание службы WCF, размещенной в IIS
Процесс разработки и развертывания службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] , которая размещается в службах IIS, состоит из следующих задач.  
  
-   Проверка правильности установки и регистрации служб IIS, ASP, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]и компонента активации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Создание нового приложения IIS или повторное использование существующего приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  
  
-   Создание SVC-файла для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Развертывание реализации службы в приложение IIS.  
  
-   Настройка службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
 Подробное пошаговое руководство по созданию службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенной в IIS, см. в разделе [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Проверка правильности установки и регистрации IIS, ASP.NET и WCF  
 Для правильной работы служб[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенных в IIS, должны быть установлены [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , IIS и ASP.NET. Процедуры установки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (как части платформы [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET и IIS зависят от используемой версии операционной системы. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] установке [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]см. в разделе [Веб-установщик Microsoft .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=201185). Инструкции по установке IIS см. в разделе [Установка IIS](http://go.microsoft.com/fwlink/?LinkId=201188).  
  
 В процессе установки платформы [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] выполняется автоматическая регистрация [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с IIS, если IIS уже имеется на компьютере. Если IIS устанавливается после платформы [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], для регистрации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с IIS и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]требуется дополнительный шаг. Это можно выполнить указанным ниже способом в зависимости от операционной системы.  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7 и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: используйте [средство регистрации ServiceModel (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) средства для регистрации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] со службами IIS: для использования этого средства, введите **ServiceModelReg.exe/i /x** в Командная строка Visual Studio. Можно открыть окно командной строки, щелкнув кнопку «Пуск» и выбрав **Все программы**, **Microsoft Visual Studio 2012**, **Набор средств Visual Studio**и **Командная строка Visual Studio**.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: установите подкомпонент "Компоненты активации Windows Communication Foundation" платформы [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Для этого на панели управления щелкните значок **Установка и удаление программ** и затем **добавить\/компонентов Windows**. При этом активируется **Мастер компонентов Windows**.  
  
-   Windows 7:  
  
 Наконец, необходимо убедиться в том, что среда ASP.NET настроена для использования платформы .NET Framework 4. Для этого запустите средство ASPNET_Regiis с параметром -i. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Средство регистрации ASP.NET IIS](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Создание нового приложения служб IIS или повторное использование существующего приложения ASP.NET  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенные в IIS, должны находиться в приложении IIS. Можно создать новое приложение IIS только для размещения служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] . Можно также развернуть службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в существующее приложение, в котором уже размещено содержимое [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] (например, страницы ASPX и веб-службы ASP.NET [ASMX]). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] этих возможностях см. в разделах "Совместное размещение служб WCF вместе с ASP.NET" и "Размещение служб WCF в режиме совместимости с ASP.NET" в [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Обратите внимание, что [!INCLUDE[iis601](../../../../includes/iis601-md.md)] и более поздние версии периодически перезагружают изолированное приложение объектно-ориентированного программирования. Значение по умолчанию — 1740 минут. Максимальное поддерживаемое значение - 71582 минуты. Этот перезапуск можно отключить. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] этом свойстве см. в разделе [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Создание SVC-файла для службы WCF  
 Службы[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенные в IIS, представляются внутри приложения IIS в виде файлов со специальным содержимым (SVC-файлов). Эта модель подобна модели, согласно которой страницы ASMX представляются внутри приложения IIS в виде ASMX-файлов. SVC-файл содержит относящуюся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]директиву обработки ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)), позволяющую инфраструктуре размещения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] активировать размещенные службы в ответ на входящие сообщения. В приведенном ниже операторе показан наиболее распространенный синтаксис SVC-файла.  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 Он содержит директиву [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) и один атрибут, `Service`. Значение атрибута `Service` - имя типа среды CLR реализации службы. Использование этой директивы по существу эквивалентно созданию основного приложения службы с помощью следующего кода.  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 Можно также создать дополнительную конфигурацию размещения, например список базовых адресов службы. Кроме того, можно применить пользовательскую фабрику <xref:System.ServiceModel.Activation.ServiceHostFactory> , чтобы расширить директиву для использования с пользовательскими решениями по размещению. Приложения IIS, в которых размещаются службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , не отвечают за управление созданием и временем существования экземпляров <xref:System.ServiceModel.ServiceHost> . Управляемая инфраструктура размещения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает необходимый экземпляр <xref:System.ServiceModel.ServiceHost> динамически при получении первого запроса для SVC-файла. Этот экземпляр не освобождается, пока он не будет явно закрыт кодом или не перезапустится приложение.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] синтаксисе SVC-файлов см. в разделе [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Развертывание реализации службы в приложение IIS  
 Для служб[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенных в IIS, используется та же модель динамической компиляции, что и для [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Точно так же, как при использовании [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], код реализации для размещенных в IIS служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно развернуть несколькими способами в разных расположениях следующим образом.  
  
-   В виде предкомпилированного DLL-файла, расположенного в глобальном кэше сборок или в каталоге \bin приложения. Предкомпилированные двоичные файлы не обновляются, пока не будет развернута новая версия библиотеки классов.  
  
-   В виде нескомпилированных исходных файлов, расположенных в каталоге \App_Code приложения. Исходные файлы, расположенные в этом каталоге, запрашиваются динамически при обработке первого запроса приложения. Любые изменения в файлах в каталоге \App_Code приводят к перезапуску и повторной компиляции всего приложения при получении следующего запроса.  
  
-   В виде нескомпилированного кода, расположенного непосредственно в SVC-файле. Код реализации может также быть размещен в SVC-файле службы после @ServiceHost директивы. Любые изменения во встроенном коде приводят к перезапуску и повторной компиляции приложения при получении следующего запроса.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] модели компиляции [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] см. в разделе [Общие сведения о компиляции в ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Настройка службы WCF  
 Конфигурация размещенных в IIS служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] хранится в файле Web.config приложений. Для размещенных в IIS служб используются те же элементы конфигурации и синтаксис, что и для служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенных вне IIS. Однако для среды размещения IIS присущи следующие ограничения.  
  
-   Базовые адреса размещенных в IIS служб.  
  
-   Приложениям, использующим [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы за пределами служб IIS, могут управлять базовый адрес в них служб, передавая набор базы адресов URI для <xref:System.ServiceModel.ServiceHost> конструктора или путем ввода [ \<узла >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) элемент конфигурации службы. Службы, размещенные в IIS, не могут управлять своими базовыми адресами; базовым адресом службы, размещенной в IIS, является адрес ее SVC-файла.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Адреса конечных точек для служб, размещенных в IIS  
 Будучи размещенными в IIS, адреса конечных точек всегда считаются относительными для адреса SVC-файла, представляющего службу. Например, если базовым адресом службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является адрес http://localhost/Application1/MyService.svc со следующей конфигурацией конечной точки.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Эта конфигурация предоставляет конечную точку, которая может быть достигнута по адресу "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 Аналогично, элемент конфигурации конечной точки, в котором в качестве относительного адреса используется пустая строка, обеспечивает конечную точку, достижимую по адресу http://localhost/Application1/MyService.svc, который является базовым адресом.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Для конечных точек служб, размещенных в IIS, следует всегда использовать относительные адреса. Предоставление полного адреса конечной точки (например, http://localhost/MyService.svc) может привести к ошибкам при развертывании службы, если адрес конечной точки не соответствует IIS-приложению, в котором размещается служба, представляющая эту конечную точку. Использование относительных адресов конечных точек для размещенных служб позволяет избежать таких потенциальных конфликтов.  
  
### <a name="available-transports"></a>Доступные типы транспорта  
 Службы[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , размещенные в IIS 5.1 и [!INCLUDE[iis601](../../../../includes/iis601-md.md)] , могут использовать связь только по протоколу HTTP. В этих платформах IIS настройка размещенной службы на использование привязки, отличной от HTTP, приводит к ошибке во время активации службы. Для [!INCLUDE[iisver](../../../../includes/iisver-md.md)]поддерживается транспорт HTTP, Net.TCP, Net.Pipe, Net.MSMQ и msmq.formatname для обратной совместимости с существующими приложениями MSMQ.  
  
### <a name="http-transport-security"></a>Безопасность транспорта HTTP  
 Размещенные в IIS службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут пользоваться средствами обеспечения безопасности транспорта HTTP (например, такими схемами проверки подлинности HTTPS и HTTP, как "Обычная проверка подлинности", "Дайджест-проверка подлинности" и "Встроенная проверка подлинности Windows"), если виртуальный каталог IIS, содержащий службу, поддерживает названные параметры. Параметры безопасности транспорта HTTP в привязке размещенной конечной точки должны соответствовать параметрам безопасности транспорта в виртуальном каталоге IIS, который содержит эту привязку.  
  
 Например, конечная точка [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , настроенная на использование дайджест-проверки подлинности HTTP, должна находиться в виртуальном каталоге IIS, который также настроен на разрешение дайджест-проверки подлинности HTTP. Несоответствующие сочетания параметров IIS и параметров конечной точки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводят к ошибке во время активации службы.  
  
## <a name="see-also"></a>См. также  
 [Размещение в службах IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Рекомендации по размещению в службах IIS](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
