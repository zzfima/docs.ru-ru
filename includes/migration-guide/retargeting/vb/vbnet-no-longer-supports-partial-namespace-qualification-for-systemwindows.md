---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236742"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5.2 в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен. Например, ссылка на <code>Windows.Forms.DialogResult</code> завершится ошибкой. Вместо этого код должен ссылаться на полное доменное имя (<xref:System.Windows.Forms.DialogResult>) или импортировать конкретное пространство имен и сослаться просто на <xref:System.Windows.Forms.DialogResult?displayProperty=name>.|
|Предложение|Следует обновить код для ссылки на API <code>System.Windows</code> либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.|
|Область|Дополнительный номер|
|Версия|4.5.2|
|Тип|Изменение целевой платформы|
