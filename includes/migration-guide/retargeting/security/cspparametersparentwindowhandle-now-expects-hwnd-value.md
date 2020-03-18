---
ms.openlocfilehash: 72f907c117748fb19ca0663f24445a8c978afd32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235568"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle теперь ожидает значение HWND

|   |   |
|---|---|
|Подробнее|Значение <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна. Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может задавать свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> с кодом, как в следующем примере:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>В предыдущих версиях платформы .NET Framework ожидалось значение <xref:System.IntPtr?displayProperty=name>, указывающее расположение в памяти, где находится значение [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). В Windows 7 и более ранних версиях задание свойству значения form.Handle ни на что не влияло, но в Windows 8 и более поздних версиях оно приводит к исключению &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=name> с сообщением "Неверный параметр".&quot;|
|Предложение|В приложениях, предназначенных для .NET Framework 4.7 или более поздней версии, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Пользователи, которые определили, что правильным значением для передачи был адрес области памяти, в которой содержалось значение <code>form.Handle</code>, могут отказаться от этого изменения в поведении, установив для параметра AppContext <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> значение <code>true</code>:<ol><li>Путем программной установки параметров совместимости в AppContext, как описано [здесь](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</li><li>путем добавления следующей строки в раздел <code>&lt;runtime&gt;</code> файла app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Пользователи, которые хотят использовать новое поведение в среде выполнения .NET Framework 4.7, когда приложения загружаются в более ранних версиях платформы .NET Framework, могут задать переключателю AppContext значение <code>false</code>.|
|Область|Дополнительный номер|
|Version|4.7|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
