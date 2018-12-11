---
title: Получение образцов баз данных SQL Server, примеры кода ADO.NET
description: Загрузите примеры баз данных SQL Server, используемые в примерах кода в документации по ADO.NET, а также средства SQL Server и управления
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 8ab65f992c9cf2b65271a237fa06eb96e358ae6a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153492"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Получение образцов баз данных, примеры кода ADO.NET

Ряд примеров и пошаговых руководствах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использовать документацию, образцы баз данных SQL Server и SQL Server Express. Можно загрузить эти продукты бесплатно от корпорации Майкрософт.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Получение образца базы данных Northwind для SQL Server

Скачайте сценарий `instnwnd.sql` из следующий репозиторий GitHub для создания и загрузки образца базы данных Northwind для SQL Server:

[Northwind и pubs образцы баз данных для Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Перед использованием базы данных Northwind, необходимо запустить Скачанный `instnwnd.sql` файла скрипта для воссоздания базы данных на экземпляре SQL Server с помощью [SQL Server Management Studio](#get_ssms) или аналогичное средство. Следуйте инструкциям в файле Readme в репозитории.

> [!TIP]
> Если вам нужны для базы данных "Борей" для Microsoft Access, см. в разделе [установить образец базы данных "Борей" для Microsoft Access](#northwind_access).

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Получить образец базы данных AdventureWorks для SQL Server

Загрузите образец базы данных AdventureWorks для SQL Server из следующего репозитория GitHub:

[Образцы баз данных AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

После загрузки одной из резервной копии базы данных (\*BAK-файл) файлов, восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS). См. в разделе [получить SQL Server Management Studio](#get_ssms).

## <a name="get_sql"></a> Получить SQL Server Express

SQL Server Express — это бесплатная, начального уровня выпуск SQL Server, можно распространять вместе с приложениями. Загрузите SQL Server Express со следующей страницы:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB включено в бесплатный выпуск Community для Visual Studio, а также выпуски Professional и более поздних версий.  

## <a name="get_ssms"></a> Получить SQL Server Management Studio
Если вы хотите просмотреть или изменить базу данных, который вы скачали, можно использовать SQL Server Management Studio (SSMS). Скачайте SSMS на следующей странице:

[Скачать SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

Можно также просматривать и управлять базами данных в среде разработки Visual Studio (IDE). В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), соединиться с базой данных из **обозреватель объектов SQL Server**, или создайте подключение данных к базе данных в **обозревателя серверов**. Эти панели обозревателя из **представление** меню.

## <a name="northwind_access"></a> Установка образца базы данных "Борей" для Microsoft Access

Образец базы данных "Борей" для Microsoft Access не доступны в центре загрузки Майкрософт. Чтобы установить Northwind непосредственно из приложения Access, выполните следующие действия:

1. Откройте доступ.

1. Ввод **Northwind** в **поиск шаблонов в Интернете** поле, а затем выберите **ввод**.

1. На странице результатов выберите **Northwind**. Откроется новое окно с описанием базы данных "Борей".

1. В новом окне в **имя файла** текстовое поле, укажите имя файла для копии базы данных "Борей".

1. Выберите **Создать**. Доступ загрузки базы данных Northwind и готовит файл.

1. По завершении этого процесса база данных открывается экран с.

## <a name="see-also"></a>См. также

- [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
