---
title: Использование инфраструктуры System.Transactions в среде ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 2bddebc13897408839e18f42b17a9fbaefdc5b87
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040408"
---
# <a name="using-systemtransactions-in-aspnet"></a>Использование инфраструктуры System.Transactions в среде ASP.NET
В этом разделе описывается, как можно успешно использовать инфраструктуру <xref:System.Transactions> в приложении ASP.NET.

## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Включение разрешения DistributedTransactionPermission в ASP.NET
 Сборка <xref:System.Transactions> поддерживает частично доверенных вызывающих и отмечена атрибутом `AllowPartiallyTrustedCallers` (APTCA). Уровни доверия для <xref:System.Transactions> определяются на основе типов ресурсов (например, системной памяти, общих ресурсов для всего процесса, системных ресурсов и других ресурсов), которые <xref:System.Transactions> предоставляет и уровень доверия, который должен быть необходим для доступа к ним. источников. В среде с частичным доверием сборка с неполным доверием может использовать только транзакции внутри домена приложения (в этом случае единственным защищаемым ресурсом является системная память), пока этой сборке не будет предоставлено разрешение <xref:System.Transactions.DistributedTransactionPermission>.

 Разрешение<xref:System.Transactions.DistributedTransactionPermission> запрашивается при каждой передаче управления транзакцией координатору распределенных транзакций (Майкрософт) (MSDTC). В этом сценарии используются ресурсы, общие для всего процесса, и прежде всего один глобальный ресурс, зарезервированный в журнале MSDTC, например внешнее веб-приложение для взаимодействия с базой данных или приложение, использующее базу данных в рамках предоставляемых им служб.

 У среды ASP.NET имеется собственный набор уровней доверия, с которыми с помощью файлов политики связан определенный набор разрешений. Дополнительные сведения см. в разделе [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). При первоначальной установке Windows SDK ни один из файлов политики ASP.NET по умолчанию не связан с <xref:System.Transactions.DistributedTransactionPermission>. Поэтому передачу управления транзакцией приложения ASP.NET координатору MSDTC выполнить не удается — возникает исключение <xref:System.Security.SecurityException> при запросе разрешения <xref:System.Transactions.DistributedTransactionPermission>. Чтобы обеспечить передачу транзакции на следующий уровень иерархии среды ASP.NET с частичным доверием, необходимо предоставить разрешение <xref:System.Transactions.DistributedTransactionPermission> для уровней доверия по умолчанию, у которых есть разрешение <xref:System.Data.SqlClient.SqlClientPermission>. Можно настроить пользовательский уровень доверия и файл политики для его поддержки или изменить файлы политики по умолчанию **Web_hightrust.config** и **Web_mediumtrust.config**.

 Чтобы изменить файлы политики, добавьте элемент `SecurityClass` для `DistributedTransactionPermission` в элемент `SecurityClasses` в элементе `PolicyLevel` и добавьте соответствующий элемент `IPermission` в ASP.NET `NamedPermissionSet` для System. Transactions. Это показано в следующем файле конфигурации.

```xml
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

 Дополнительные сведения о политике безопасности ASP.NET см. в разделе [элемент SecurityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).

## <a name="dynamic-compilation"></a>Динамическая компиляция
 Чтобы импортировать и использовать <xref:System.Transactions> в приложении ASP.NET, динамически компилируемом во время доступа, в файле конфигурации необходимо указать ссылку на сборку <xref:System.Transactions>. В частности, ссылка должна добавляться в раздел `compilation/assemblies` корневого файла конфигурации **Web. config** по умолчанию или в файл конфигурации конкретного веб-приложения. В следующем примере это показано.

```xml
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

 Дополнительные сведения см. в разделе [Добавление элемента для сборок для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).

## <a name="see-also"></a>См. также

- [ASP.NET уровни доверия и файлы политик](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [Элемент securityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Передача управления транзакцией на следующий уровень иерархии](transaction-management-escalation.md)
