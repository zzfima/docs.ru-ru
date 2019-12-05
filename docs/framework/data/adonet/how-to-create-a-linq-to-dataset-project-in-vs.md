---
title: Создание проекта LINQ to DataSet в Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 91032766248b11e51b90aa788b1c64c140347c25
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802024"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Руководство. Создание проекта LINQ to DataSet в Visual Studio

Для различных типов проектов LINQ требуются определенные ссылки на сборки и импортированные пространства имен (Visual Basic) или директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (C#). Минимальное требование LINQ — это ссылка на *библиотеку System. Core. dll* и директиву `using` для <xref:System.Linq>.

Эти требования предоставляются по умолчанию при создании нового C# проекта консольного приложения в Visual Studio 2017 или более поздней версии. Если вы обновляете проект с более ранней версии Visual Studio, вам может потребоваться предоставить эти ссылки, связанные с LINQ, вручную.

LINQ to DataSet требуется две дополнительные ссылки на *System. Data. dll* и *System. Data. DataSetExtensions. dll*.

> [!NOTE]
> При построении из командной строки необходимо вручную ссылаться на библиотеки DLL, связанные с LINQ, в *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Включение функциональности LINQ to DataSet

Выполните следующие действия, чтобы включить LINQ to DataSet функциональности в существующем проекте.

1. Добавьте ссылки на **System. Core**, **System. Data**и **System. Data. DataSetExtensions**.

   В **Обозреватель решений**щелкните правой кнопкой мыши узел **ссылки** и выберите команду **Добавить ссылку**. В диалоговом окне **Диспетчер ссылок** выберите **System. Core**, **System. Data**и **System. Data. DataSetExtensions**. Нажмите кнопку **ОК**.

1. Добавьте директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (или [импортирует операторы](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в Visual Basic) для **System. Data** и **System. LINQ**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. При необходимости добавьте директиву `using` (или `Imports` инструкцию) для **System. Data. Common** или **System. Data. SqlClient**в зависимости от способа подключения к базе данных.

## <a name="see-also"></a>См. также:

- [Начало работы с LINQ to DataSet](getting-started-linq-to-dataset.md)
