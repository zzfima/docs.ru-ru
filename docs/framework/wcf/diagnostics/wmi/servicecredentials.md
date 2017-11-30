---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
