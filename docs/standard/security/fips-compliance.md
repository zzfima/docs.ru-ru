---
title: Соответствие FIPS — .NET Core
description: Описывает соответствие стандартам федеральной информационной обработки (FIPS) .NET Core.
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626962"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>Соответствие стандарту федеральной обработки информации (FIPS) .NET Core

Версия федерального стандарта обработки информации (FIPS) 140-2 — это стандарт правительства США, который определяет минимальные требования к безопасности для криптографических модулей в продуктах информационных технологий, как определено в разделе 5131 информации. Новые функции управления технологиями — 1996.

.NET Core:

* Передает вызовы примитивов шифрования в стандартные модули, предоставляемые базовой операционной системой.
* **Не** обеспечивает использование алгоритмов и размеров ключей, утвержденных FIPS, в приложениях .NET Core.

Системный администратор несет ответственность за настройку соответствия FIPS для операционной системы.

Если код написан для совместимой с FIPS среды, разработчик несет ответственность за то, чтобы не использовать несоответствующие алгоритмы FIPS.

Дополнительные сведения о соответствии требованиям FIPS см. в следующих статьях:

* [Соответствие требованиям Windows FIPS](/windows/security/threat-protection/fips-140-validation)
* [Настройка Windows для соответствия требованиям FIPS](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [Глава 8. Федеральные стандарты и нормативы Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
