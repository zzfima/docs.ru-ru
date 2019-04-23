---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772106"
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
  
 Тип доступа: Только чтение  
  
 Параметры проверки подлинности сертификата клиента и подготовки для этой службы.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Параметры проверки подлинности текущего выданного маркера для этой службы.  
  
### <a name="peer"></a>Одноранговый узел  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает текущие параметры безопасного обмена данными.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Сертификат, связанный с этой службой.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Параметры проверки имени пользователя и пароля для данной службы.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Параметры проверки подлинности Windows для этой службы.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ServiceCredentials>
