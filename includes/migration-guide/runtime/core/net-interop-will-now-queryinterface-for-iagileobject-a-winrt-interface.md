---
ms.openlocfilehash: 0036fc2b03dde64d24d883e55b9f00c931f0c218
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997701"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>Взаимодействие .NET теперь будет использовать QueryInterface для IAgileObject (интерфейс WinRT)

|   |   |
|---|---|
|Подробнее|При использовании события WinRT с делегатом .NET Windows будет использовать QI для IAgileObject начиная с .NET Framework 4.8.  В предыдущих версиях .NET Framework среда выполнения некорректно обрабатывала QI и на событие невозможно было подписаться.<ul><li>[x] Режим совместимости</li></ul>|
|Предложение|Если включение QI для IAgileObject прерывает выполнение, этот код можно отключить, задав следующую конфигурацию. <h4>Метод 1. переменная среды;</h4> Установите следующую переменную среды: COMPLUS_DisableCCWSupportIAgileObject=1. Этот метод влияет на любую среду, которая наследует эту переменную среды. Это может быть только один консольный сеанс или весь компьютер, если задать переменную среды глобально. Имя переменной среды не учитывает регистр. <h4>Метод 2. Реестр</h4> В редакторе реестра (regedit.exe) найдите один из следующих подключей: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework. Затем добавьте следующее: Имя значения: DisableCCWSupportIAgileObject. Тип: DWORD (32-разрядный). Значение (также называется REG_WORD). Значение: 1. Вы можете использовать средство Windows REG.EXE, чтобы добавить это значение из командной строки или среды сценария. Пример:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>В этом случае <code>HKLM</code> используется вместо <code>HKEY_LOCAL_MACHINE</code>. Для просмотра справки по этому синтаксису используйте <code>reg add /?</code>. Имя значения реестра обрабатывается без учета регистра.|
|Область|Пограничный случай|
|Version|4.8|
|Type|Среда выполнения|
