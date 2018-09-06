---
title: Практическое руководство. Блокировка конечных точек в среде предприятия
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 032b69c1fae38576b0374b329f1ab6fe90e2b1a0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43806203"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Практическое руководство. Блокировка конечных точек в среде предприятия
Крупным предприятиям часто требуется, чтобы приложения разрабатывались в соответствии с политиками безопасности предприятия. Следующий раздел описывает, как разрабатывать и устанавливать проверяющий элемент конечной точки клиента, который может использоваться для проверки всех клиентских приложений Windows Communication Foundation (WCF), установленного на компьютерах.  
  
 В этом случае проверяющий элемент управления является клиентский элемент управления, поскольку поведение этой конечной точки добавляется клиенту [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) раздел в файле machine.config. WCF загружает общие поведения конечных точек только для клиентских приложений и загружает общие поведения служб только для приложений служб. Чтобы установить тот же проверяющий элемент управления для приложения службы, этот элемент управления должен представлять собой поведение службы. Дополнительные сведения см. в разделе [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) раздел.  
  
> [!IMPORTANT]
>  Поведения службы или конечной точки, не помеченные <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA), добавляются к [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) раздел файла конфигурации не запускаются, когда приложение выполняется в режиме частичного доверия Среда и исключение не возникает, когда это происходит. Чтобы принудительно запустить общие поведения, такие как проверяющие элементы управления, необходимо выполнить одно из следующих условий.  
>   
>  -- Пометить общее поведение атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, чтобы оно могло выполняться при развертывании в приложении с частичным доверием. Обратите внимание, что на компьютере может быть установлен соответствующий параметр реестра, чтобы на нем не могли выполняться сборки, помеченные атрибутом APTCA.  
>   
>  -- Проверить, что при развертывании приложения в качестве приложения с полным доверием, которое не может изменяться пользователям, параметры управления доступом для кода разрешают выполнение приложения в среде с частичным доверием. Если это так, пользовательский проверяющий элемент управления не выполняется и исключение не создается. Один из способов, см. в разделе `levelfinal` использование параметра [средство политики безопасности доступа кода (Caspol.exe)](https://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Дополнительные сведения см. в разделе [рекомендации по частичному доверию](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) и [Поддерживаемые сценарии развертывания](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### <a name="to-create-the-endpoint-validator"></a>Создание проверяющего элемента конечной точки  
  
1.  Создайте расширение <xref:System.ServiceModel.Description.IEndpointBehavior>, в методе <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> которого выполняются необходимые действия по проверке. Ниже приведен пример кода. ( `InternetClientValidatorBehavior` Берется из [проверки безопасности](../../../../docs/framework/wcf/samples/security-validation.md) пример.)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Создает новый класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который регистрирует проверяющий элемент управления конечной точки на шаге 1. Это показано в следующем примере кода. (Исходный код для этого примера находится в [проверки безопасности](../../../../docs/framework/wcf/samples/security-validation.md) пример.)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Проверьте, что скомпилированная сборка подписана строгим именем. Дополнительные сведения см. в разделе [Strong Name Tool (SN. (EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) и команд компилятора для вашего языка.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>Установка проверяющего элемента управления на целевом компьютере  
  
1.  Установите проверяющий элемент конечной точки, используя соответствующую процедуру. На предприятии для этого можно использовать групповую политику или сервер Systems Management Server (SMS).  
  
2.  Установите сборку со строгим именем в глобальный кэш с помощью [Gacutil.exe (программа глобального кэша сборок)](https://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).  
  
3.  С помощью типов из пространства имен <xref:System.Configuration?displayProperty=nameWithType> выполните следующие действия.  
  
    1.  Добавить расширение для [ \<behaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) с помощью имени типа, полное и заблокируйте элемент.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Добавьте элемент поведения `EndpointBehaviors` свойство [ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) и заблокируйте элемент. (Чтобы установить проверяющий элемент управления в службе, он должен являться реализацией интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> и должен быть добавлен в свойство `ServiceBehaviors`.) В следующем примере кода показана правильная конфигурация после выполнения шагов A и B с единственным исключением, что в ней нет строгого имени.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Сохраните файл machine.config. В следующем примере кода выполняются все действия шага 3, но копия измененного файла machine.config сохраняется локально.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить общее поведение в файл machine.config и сохранить копию файла на диске. `InternetClientValidatorBehavior` Берется из [проверки безопасности](../../../../docs/framework/wcf/samples/security-validation.md) образца.  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Может также возникнуть необходимость зашифровать элементы файла конфигурации. Дополнительные сведения см. в разделе «См. также».  
  
## <a name="see-also"></a>См. также  
 [Шифрование элементов файла конфигурации, с помощью DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)  
 [Шифрование элементов файла конфигурации, с помощью RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
