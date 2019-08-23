---
title: Практическое руководство. Блокировка конечных точек в среде предприятия
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 6a74df56d4c283569988d310b2a501e6440f58ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951659"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Практическое руководство. Блокировка конечных точек в среде предприятия
Крупным предприятиям часто требуется, чтобы приложения разрабатывались в соответствии с политиками безопасности предприятия. В следующем разделе описывается разработка и установка проверяющего элемента управления конечной точки клиента, который может использоваться для проверки всех клиентских приложений Windows Communication Foundation (WCF), установленных на компьютерах.  
  
 В этом случае проверяющий элемент управления является проверяющим элементом управления клиента, так как это поведение конечной точки добавляется в раздел Client [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) в файле Machine. config. WCF загружает общие поведения конечной точки только для клиентских приложений и загружает общие поведения службы только для приложений служб. Чтобы установить тот же проверяющий элемент управления для приложения службы, этот элемент управления должен представлять собой поведение службы. Дополнительные сведения см. в [ \<разделе commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) .  
  
> [!IMPORTANT]
> Поведения служб или конечных точек, не <xref:System.Security.AllowPartiallyTrustedCallersAttribute> помеченные атрибутом (APTCA), которые [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) добавляются в раздел > commonBehaviors файла конфигурации, не запускаются, если приложение выполняется в среде с частичным доверием и нет исключение возникает в этом случае. Чтобы принудительно запустить общие поведения, такие как проверяющие элементы управления, необходимо выполнить одно из следующих условий.  
>   
>  -- Пометить общее поведение атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, чтобы оно могло выполняться при развертывании в приложении с частичным доверием. Обратите внимание, что на компьютере может быть установлен соответствующий параметр реестра, чтобы на нем не могли выполняться сборки, помеченные атрибутом APTCA.  
>   
>  -- Проверить, что при развертывании приложения в качестве приложения с полным доверием, которое не может изменяться пользователям, параметры управления доступом для кода разрешают выполнение приложения в среде с частичным доверием. Если это так, пользовательский проверяющий элемент управления не выполняется и исключение не создается. Чтобы убедиться в этом, ознакомьтесь `levelfinal` с параметром использование [средства политики управления доступом для кода (Caspol. exe)](https://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Дополнительные сведения см. в разделе [рекомендации](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) по частичному доверию и [Поддерживаемые сценарии развертывания](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### <a name="to-create-the-endpoint-validator"></a>Создание проверяющего элемента конечной точки  
  
1. Создайте расширение <xref:System.ServiceModel.Description.IEndpointBehavior>, в методе <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> которого выполняются необходимые действия по проверке. Ниже приведен пример кода. (Объект `InternetClientValidatorBehavior` берется из примера [проверки безопасности](../../../../docs/framework/wcf/samples/security-validation.md) .)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2. Создает новый класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который регистрирует проверяющий элемент управления конечной точки на шаге 1. Это показано в следующем примере кода. (Исходный код для этого примера находится в примере [проверки безопасности](../../../../docs/framework/wcf/samples/security-validation.md) .)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3. Проверьте, что скомпилированная сборка подписана строгим именем. Дополнительные сведения см. в разделе [средство строгих имен (Sn. EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) и команды компилятора для вашего языка.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>Установка проверяющего элемента управления на целевом компьютере  
  
1. Установите проверяющий элемент конечной точки, используя соответствующую процедуру. На предприятии для этого можно использовать групповую политику или сервер Systems Management Server (SMS).  
  
2. Установите сборку со строгим именем в глобальный кэш сборок с помощью программы [gacutil. exe (средство глобального кэша сборок)](../../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
3. С помощью типов из пространства имен <xref:System.Configuration?displayProperty=nameWithType> выполните следующие действия.  
  
    1. Добавьте расширение в [ \<раздел > бехавиорекстенсионс](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) с помощью полного имени типа и заблокируйте элемент.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2. Добавьте элемент Behavior в `EndpointBehaviors` свойство [ \<раздела commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) и заблокируйте элемент. (Чтобы установить проверяющий элемент управления в службе, он должен являться реализацией интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> и должен быть добавлен в свойство `ServiceBehaviors`.) В следующем примере кода показана правильная конфигурация после выполнения шагов A и B с единственным исключением, что в ней нет строгого имени.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3. Сохраните файл machine.config. В следующем примере кода выполняются все действия шага 3, но копия измененного файла machine.config сохраняется локально.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить общее поведение в файл machine.config и сохранить копию файла на диске. Берется из примера [проверки безопасности.](../../../../docs/framework/wcf/samples/security-validation.md) `InternetClientValidatorBehavior`  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Может также возникнуть необходимость зашифровать элементы файла конфигурации. Дополнительные сведения см. в разделе «См. также».  
  
## <a name="see-also"></a>См. также

- [Шифрование элементов файла конфигурации с помощью DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)
- [Шифрование элементов файла конфигурации с помощью RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
