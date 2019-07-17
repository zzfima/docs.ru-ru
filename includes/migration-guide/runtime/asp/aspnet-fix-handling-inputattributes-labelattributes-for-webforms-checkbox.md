---
ms.openlocfilehash: e605e0f2636d83745815ec4ed27bf72692f18d15
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802599"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>ASP.NET. Исправление обработки InputAttributes и LabelAttributes для элемента управления "Флажок" в веб-формах

|   |   |
|---|---|
|Подробные сведения|Для приложений, предназначенных для .NET Framework 4.7.2 и более ранних версий, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, добавленные в элемент управления <xref:System.Web.UI.WebControls.CheckBox> веб-форм программными средствами, теряются после обратной передачи. Для приложений, предназначенных для .NET Framework 4.8 или более поздних версий, они сохраняются после обратной передачи.|
|Предложение|Для правильного поведения для восстановления атрибутов при обратной передаче задайте <code>targetFrameworkVersion</code> 4.8 или более позднюю версию. Например:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Если установить значение ниже или не установить никакое значение, сохраняется старое неправильное поведение.|
|Область|Неизвестно|
|Версия|4.8|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|

