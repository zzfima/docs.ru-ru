---
ms.openlocfilehash: 6fafb689af5d50b31b19f5d1fe7090a6c256ca45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804882"
---
### <a name="wpf-printing-stack-update"></a>Обновления стека печати WPF

|   |   |
|---|---|
|Подробные сведения|API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=name>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS. Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API. Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update. Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.|
|Предложение|Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Среда выполнения|
