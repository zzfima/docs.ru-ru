---
title: Элемент <httpDigest>
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 914711e4d6c3dbb1ccc741af1b3abd6b8de716a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751050"
---
# <a name="httpdigest-element"></a>\<httpDigest> Element
Задает учетные данные, используемые для дайджест-проверки подлинности клиента при подключении к службе.  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<endpointBehaviors>  
\<поведение >  
\<clientCredentials>  
\<httpDigest>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`impersonationLevel`|Задает параметры олицетворения, сообщаемые клиентом серверу. Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера. Допустимы следующие значения:<br /><br /> -Идентификация: Сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиента.<br />-Олицетворения: Сервер может олицетворять контекст безопасности клиента в локальной системе.<br />-Делегирование: Сервер может олицетворять контекст безопасности клиента в удаленных системах.<br />-Анонимный: Сервер не может олицетворять или идентифицировать клиента.<br />-None: Уровень олицетворения не назначается.<br /><br /> Значение по умолчанию - Identification. Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Хэш-кода — это хэш, определяемый с помощью алгоритма и набора входных данных. Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных. Клиент может вычислить хэш и отправить его службе. Служба также вычисляет хэш и сравнивает значения. Совпадение значений подтверждает подлинность клиента.  
  
 Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS. Дополнительные сведения см. в разделе [дайджест-проверка подлинности в IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)
- [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
