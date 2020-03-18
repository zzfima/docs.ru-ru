---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802599"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>ASP.NET. Исправление обработки InputAttributes и LabelAttributes для элемента управления "Флажок" в веб-формах

|   |   |
|---|---|
|Подробнее|Для приложений, предназначенных для .NET Framework 4.7.2 и более ранних версий, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, добавленные в элемент управления <xref:System.Web.UI.WebControls.CheckBox> веб-форм программными средствами, теряются после обратной передачи. Для приложений, предназначенных для .NET Framework 4.8 или более поздних версий, они сохраняются после обратной передачи.|
|Предложение|Для правильного поведения для восстановления атрибутов при обратной передаче задайте <code>targetFrameworkVersion</code> 4.8 или более позднюю версию. Пример:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Если установить значение ниже или не установить никакое значение, сохраняется старое неправильное поведение.|
|Область|Неизвестно|
|Version|4.8|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
