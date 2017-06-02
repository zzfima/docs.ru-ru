---
title: "Использование инфраструктуры System.Transactions в среде ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Использование инфраструктуры System.Transactions в среде ASP.NET
В этом разделе описывается, как можно эффективно использовать пространство имен <xref:System.Transactions> в приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
## Включение разрешения DistributedTransactionPermission в ASP.NET  
 Сборка <xref:System.Transactions> поддерживает частично доверенных вызывающих и отмечена атрибутом **AllowPartiallyTrustedCallers** \(APTCA\). Уровни доверия для сборки <xref:System.Transactions> определяются на основе типов ресурсов \(например, системная память, ресурсы, общие для всего процесса, ресурсы, общие для всей системы, и другие ресурсы\), которые используются в <xref:System.Transactions>, и уровня доверия, необходимого для доступа к этим ресурсам. В среде с частичным доверием сборка с неполным доверием может использовать только транзакции внутри домена приложения \(в этом случае единственным защищаемым ресурсом является системная память\), пока этой сборке не будет предоставлено разрешение <xref:System.Transactions.DistributedTransactionPermission>.  
  
 Разрешение <xref:System.Transactions.DistributedTransactionPermission> запрашивается при каждой передаче управления транзакцией координатору распределенных транзакций \(Майкрософт\) \(MSDTC\). В этом сценарии используются ресурсы, общие для всего процесса, и прежде всего один глобальный ресурс, зарезервированный в журнале MSDTC, например внешнее веб\-приложение для взаимодействия с базой данных или приложение, использующее базу данных в рамках предоставляемых им служб.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] имеет собственный набор уровней доверия, с которыми при помощи файлов политики связан определенный набор разрешений.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [ASP.NET Trust Levels and Policy Files](../Topic/ASP.NET%20Trust%20Levels%20and%20Policy%20Files.md). После первоначальной установки пакета Windows SDK ни один из файлов политики [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] по умолчанию не связан с разрешением <xref:System.Transactions.DistributedTransactionPermission>. Поэтому передачу управления транзакцией приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] координатору MSDTC выполнить не удается: возникает исключение <xref:System.Security.SecurityException> при запросе разрешения <xref:System.Transactions.DistributedTransactionPermission>. Чтобы обеспечить передачу транзакции на следующий уровень иерархии среды [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] с частичным уровнем доверия, необходимо предоставить разрешение <xref:System.Transactions.DistributedTransactionPermission> для уровней доверия по умолчанию, у которых есть разрешение <xref:System.Data.SqlClient.SqlClientPermission>. Можно настроить пользовательский уровень доверия и файл политики для его поддержки или изменить файлы политики по умолчанию **Web\_hightrust.config** и **Web\_mediumtrust.config**.  
  
 Чтобы изменить файлы политики, добавьте элемент **SecurityClass** для **DistributedTransactionPermission** в элемент **SecurityClasses** в элементе **PolicyLevel** и добавьте соответствующий элемент **IPermission** в элемент [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]**NamedPermissionSet** для System.Transactions. Это показано в следующем файле конфигурации.  
  
```  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] политике безопасности [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] см. в разделе [Элемент securityPolicy \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/469d8d22-d263-46bb-8400-40d8d027faba).  
  
## Динамическая компиляция  
 Чтобы импортировать и использовать <xref:System.Transactions> в приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], динамически компилируемом во время доступа, в файле конфигурации необходимо указать ссылку на сборку <xref:System.Transactions>. В частности, ссылку необходимо добавить в раздел **compilation**\/**assemblies** корневого файла конфигурации по умолчанию **Web.config** или файла конфигурации конкретного веб\-приложения. В следующем примере это показано.  
  
```  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Элемент add для элемента assemblies для элемента compilation \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/602197e8-108d-4249-b752-ba2a318f75e4).  
  
## См. также  
 [ASP.NET Trust Levels and Policy Files](../Topic/ASP.NET%20Trust%20Levels%20and%20Policy%20Files.md)   
 [Элемент securityPolicy \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/469d8d22-d263-46bb-8400-40d8d027faba)   
 [Передача управления транзакцией на следующий уровень иерархии ](../../../../docs/framework/data/transactions/transaction-management-escalation.md)