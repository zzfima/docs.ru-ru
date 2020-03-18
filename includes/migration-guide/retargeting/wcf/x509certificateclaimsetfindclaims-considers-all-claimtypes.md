---
ms.openlocfilehash: 9678c077e278a9d76ffd5c2ce10e63ebe3ad09f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235538"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims учитывает все аргументы claimType

|   |   |
|---|---|
|Подробнее|Если в приложениях, предназначенных для .NET Framework 4.6.1, набор утверждений X509 инициализируется из сертификата, имеющего несколько записей DNS в поле SAN, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> пытается сопоставить аргумент claimType со всеми записями DNS. В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> пытается сопоставить аргумент claimType только с последней записью DNS.|
|Предложение|Это изменение затрагивает только приложения, предназначенные для .NET Framework 4.6.1. Это изменение может быть отключено (или включено, если используются версии, предшествующие 4.6.1) с помощью параметра совместимости [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).|
|Область|Дополнительный номер|
|Version|4.6.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|
