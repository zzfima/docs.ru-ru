---
ms.openlocfilehash: 02a3c1b5a9693535feeab56d9b0f7c9d360749ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235941"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Событие Page.LoadComplete больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных

|   |   |
|---|---|
|Подробные сведения|Событие <xref:System.Web.UI.Page.LoadComplete> больше не заставляет элемент управления <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> вызывать привязку данных для изменений в параметрах создания/обновления/удаления. Это изменение исключает лишнее обращение к базе данных, не допускает сброса значений элементов управления и позволяет получить поведение, согласованное с другими элементами управления данными, такими как <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> и <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>. Это изменение дает другое поведение в том маловероятном случае, когда в приложении предполагается вызов привязки данных в событии <xref:System.Web.UI.Page.LoadComplete>.|
|Предложение|Если есть необходимость в привязке данных, вручную вызовите ее в событии, которое возникает раньше в обратной передаче.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
