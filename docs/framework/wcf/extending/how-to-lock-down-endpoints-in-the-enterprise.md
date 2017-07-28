---
title: "Как блокировать конечные точки в среде предприятия | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Как блокировать конечные точки в среде предприятия
Крупным предприятиям часто требуется, чтобы приложения разрабатывались в соответствии с политиками безопасности предприятия.  В следующем разделе описано, как разработать и установить проверяющий элемент управления конечной точки клиента, который может проверять все установленные на компьютерах клиентские приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 В этом случае проверяющим элементом управления является клиентский проверяющий элемент управления, поскольку поведение этой конечной точки добавляется[\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) файла machine.config.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] загружает общие поведения конечных точек только для клиентских приложений и загружает общие поведения служб только для приложений служб.  Чтобы установить тот же проверяющий элемент управления для приложения службы, этот элемент управления должен представлять собой поведение службы.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] раздел [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md).  
  
> [!IMPORTANT]
>  Расширения функциональности служб и конечных точек, не помеченные атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\), которые добавляются в раздел [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) файла конфигурации, не выполняются, когда приложение выполняется в среде с частичным доверием, и исключение в этом случае не возникает.  Чтобы принудительно запустить общие поведения, такие как проверяющие элементы управления, необходимо выполнить одно из следующих условий.  
>   
>  \-\- Пометить общее поведение атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, чтобы оно могло выполняться при развертывании в приложении с частичным доверием.  Обратите внимание, что на компьютере может быть установлен соответствующий параметр реестра, чтобы на нем не могли выполняться сборки, помеченные атрибутом APTCA.  
>   
>  \-\- Проверить, что при развертывании приложения в качестве приложения с полным доверием, которое не может изменяться пользователям, параметры управления доступом для кода разрешают выполнение приложения в среде с частичным доверием.  Если это так, пользовательский проверяющий элемент управления не выполняется и исключение не создается.  Один из способов обеспечения этого заключается в использовании параметра `levelfinal` с помощью [средства настройки политики управления доступом для кода \(Caspol.exe\)](http://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Дополнительные сведения см. в разделах [Рекомендации по частичному уровню доверию](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) и [Поддерживаемые сценарии развертывания](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### Создание проверяющего элемента конечной точки  
  
1.  Создайте расширение <xref:System.ServiceModel.Description.IEndpointBehavior>, в методе <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> которого выполняются необходимые действия по проверке.  Ниже приведен пример кода.  \(`InternetClientValidatorBehavior` берется из примера [Проверка безопасности](../../../../docs/framework/wcf/samples/security-validation.md).\)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Создает новый класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который регистрирует проверяющий элемент управления конечной точки на шаге 1.  Это показано в следующем примере кода.  \(Исходный код для этого примера находится в примере [Проверка безопасности](../../../../docs/framework/wcf/samples/security-validation.md).\)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Проверьте, что скомпилированная сборка подписана строгим именем.  Дополнительные сведения см. в описании средства [Strong Name Tool \(SN. \(EXE\)](http://go.microsoft.com/fwlink/?LinkId=248217) и команд компилятора для вашего языка.  
  
### Установка проверяющего элемента управления на целевом компьютере  
  
1.  Установите проверяющий элемент конечной точки, используя соответствующую процедуру.  На предприятии для этого можно использовать групповую политику или сервер Systems Management Server \(SMS\).  
  
2.  Установите сборку со строгим именем в глобальный кэш сборок с помощью программы [Gacutil.exe \(программа глобального кэша сборок\)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).  
  
3.  С помощью типов из пространства имен <xref:System.Configuration?displayProperty=fullName> выполните следующие действия.  
  
    1.  Добавьте расширение в раздел [\<behaviorExtensions\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) используя полное имя типа, и заблокируйте элемент.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Добавьте элемент поведения в свойство `EndpointBehaviors` раздела [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) и заблокируйте этот элемент.  \(Чтобы установить проверяющий элемент управления в службе, он должен являться реализацией интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> и должен быть добавлен в свойство `ServiceBehaviors`.\) В следующем примере кода показана правильная конфигурация после выполнения шагов A  и B с единственным исключением, что в ней нет строгого имени.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Сохраните файл machine.config.  В следующем примере кода выполняются все действия шага 3, но копия измененного файла machine.config сохраняется локально.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## Пример  
 В следующем примере кода показано, как добавить общее поведение в файл machine.config и сохранить копию файла на диске.  `InternetClientValidatorBehavior` берется из примера [Проверка безопасности](../../../../docs/framework/wcf/samples/security-validation.md).  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## Безопасность платформы .NET Framework  
 Может также возникнуть необходимость зашифровать элементы файла конфигурации.  Дополнительные сведения см. в разделе «См. также».  
  
## См. также  
 [Шифрование элементов файла конфигурации с помощью DPAPI](http://go.microsoft.com/fwlink/?LinkId=94954)   
 [Шифрование элементов файла конфигурации с помощью RSA](http://go.microsoft.com/fwlink/?LinkId=94955)