---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 26bd0c95f930bf7859ae6409d797afbb596844fa
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180671"
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceCredentials не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceCredentials имеет следующие свойства.  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности сертификата клиента и подготовки для этой службы.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности текущего выданного маркера для этой службы.  
  
### <a name="peer"></a>Одноранговый узел  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает текущие параметры безопасного обмена данными.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Сертификат, связанный с этой службой.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки имени пользователя и пароля для данной службы.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности Windows для этой службы.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceCredentials>
