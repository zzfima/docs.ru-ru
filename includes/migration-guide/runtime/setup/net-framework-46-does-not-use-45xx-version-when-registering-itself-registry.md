---
ms.openlocfilehash: 08c16f261338148619de2e484c73046b9d9a6bfe
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858493"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>.NET Framework 4.6 не использует версию 4.5.x.x для собственной регистрации в реестре

|   |   |
|---|---|
|Подробные сведения|Ключ версии, установленный в реестре (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) для платформы .NET Framework 4.6, ожидаемо начинается с "4.6", а не с "4.5". Приложения, которые используют эти разделы реестра для определения установленных на компьютере версий .NET Framework, следует обновить таким образом, чтобы понимать, что 4.6 — это новая возможная версия, совместимая с предыдущими выпусками 4.5.x.|
|Предложение|Обновите приложения, проверяющие установку версию .NET Framework 4.5 в соответствующих разделах реестра, так, чтобы они принимали версию 4.6.|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Среда выполнения|

