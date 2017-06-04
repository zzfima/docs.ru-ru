---
title: "Практическое руководство. Олицетворение клиента в рамках службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, олицетворение"
  - "олицетворение"
  - "WCF, безопасность"
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 33
---
# Практическое руководство. Олицетворение клиента в рамках службы
Олицетворение клиента в службе [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] позволяет службе выполнять действия от имени клиента. В случае действий, для которых предусмотрены проверки списка управления доступом \(ACL\), таким как доступ к каталогам и файлам на компьютере или доступ к базе данных SQL Server, проверка ACL выполняется с использованием клиентской учетной записи пользователя. В данном разделе представлены основные этапы установки клиентом уровня олицетворения клиента в домене Windows. Рабочий пример см. в разделе [Олицетворение клиента](../../../docs/framework/wcf/samples/impersonating-the-client.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] олицетворении клиента см. в разделе [Делегирование и олицетворение](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Если клиент и служба выполняются на одном компьютере и клиент выполняется от имени системной учетной записи \(например, `Local System` или `Network Service`\), клиент невозможно олицетворить, если установлен безопасный сеанс с маркерами контекста безопасности с отслеживанием состояния. WinForms или консольное приложение, как правило, выполняется от имени текущей зарегистрированной учетной записи, что позволяет олицетворить учетную запись по умолчанию. Если же клиент представляет собой страницу [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], размещенную в службах [!INCLUDE[iis601](../../../includes/iis601-md.md)] или IIS 7.0, клиент выполняется от имени учетной записи `Network Service` по умолчанию. Все предоставляемые системой привязки, поддерживающие защищенные сеансы, по умолчанию используют маркер контекста безопасности без отслеживания состояния. Но если клиент является страницей [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] и используются защищенные сеансы с токенами контекста безопасности с отслеживанием состояния, то олицетворение клиента невозможно.[!INCLUDE[crabout](../../../includes/crabout-md.md)] использовании маркеров контекста безопасности с отслеживанием состояния в защищенном сеансе см. в разделе [Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### Включение олицетворения клиента из кэшированного маркера Windows в службе  
  
1.  Создайте службу. Дополнительные сведения по этой базовой процедуре см. в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2.  Используйте привязку, использующую проверку подлинности Windows, и создайте сеанс, такой как <xref:System.ServiceModel.NetTcpBinding> или <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  При создании реализации интерфейса службы примените класс <xref:System.ServiceModel.OperationBehaviorAttribute> к методу, требующему олицетворения клиента. Задайте для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> значение <xref:System.ServiceModel.ImpersonationOption>.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### Установка допустимого уровня олицетворения на стороне клиента  
  
1.  Создайте код клиента службы с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Обращение к службам с использованием клиента WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  После создания клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] присвойте свойству <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> класса <xref:System.ServiceModel.Security.WindowsClientCredential> одно из значений перечисления <xref:System.Security.Principal.TokenImpersonationLevel>.  
  
    > [!NOTE]
    >  Для использования <xref:System.Security.Principal.TokenImpersonationLevel> необходимо использовать согласованную проверку подлинности Kerberos \(иногда называемую *многоступенчатой* или *многоэтапной* проверкой Kerberos\). Описание этого процесса см. в разделе [Рекомендации по безопасности](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## См. также  
 <xref:System.ServiceModel.OperationBehaviorAttribute>   
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 [Олицетворение клиента](../../../docs/framework/wcf/samples/impersonating-the-client.md)   
 [Делегирование и олицетворение](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)