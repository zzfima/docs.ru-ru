---
title: Получение образцов баз данных, примеры кода ADO.NET
description: Загрузите примеры баз данных, используемые в примерах кода в документации по ADO.NET, а также средства SQL Server и управления
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347528"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Получение образцов баз данных, примеры кода ADO.NET

Ряд примеров и пошаговых руководствах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использовать документацию, образцы баз данных и SQL Server Express. Можно загрузить эти продукты бесплатно от корпорации Майкрософт.

## <a name="get-the-adventureworks-sample-database"></a>Получить образец базы данных AdventureWorks

Загрузите образец базы данных AdventureWorks для следующего репозитория GitHub:

[Образцы баз данных AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

После загрузки одной из резервной копии базы данных (\*BAK-файл) файлов, восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS). См. в разделе [получить SQL Server Management Studio](#get_ssms).

## <a name="get-the-northwind-sample-database"></a>Получить образец базы данных "Борей"

Загрузите образец базы данных "Борей" со следующей страницы в центре загрузки Майкрософт:

[Образцы баз данных Pubs и Northwind](https://go.microsoft.com/fwlink?linkid=64296)

После загрузки файла, дважды щелкните файл, чтобы извлечь базы данных и скрипты. По умолчанию файлы устанавливаются в папке `<drive>:\SQL Server 2000 Sample Databases`.

Перед использованием базы данных Northwind, необходимо выполнить одно из следующих действий:

- Повторно создать базы данных на экземпляре SQL Server, запустив `instnwnd.sql` файл скрипта в папке установки.

- Присоединение `northwnd.mdf` файл с соответствующим ему аргументом `*.ldf` файл журнала на экземпляре SQL Server.

## <a name="get_sql"></a> Получить SQL Server Express

SQL Server Express — это бесплатная, начального уровня выпуск SQL Server, можно распространять вместе с приложениями. Загрузите SQL Server Express со следующей страницы:
  
[Выпуски SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB включается в Community edition, а также выпуски Professional и более поздних версий.  

## <a name="get_ssms"></a> Получить SQL Server Management Studio
Если вы хотите просмотреть или изменить базу данных, который вы скачали, можно использовать SQL Server Management Studio (SSMS). Скачайте SSMS на следующей странице:

[Скачать SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

Можно также просматривать и управлять базами данных в среде разработки Visual Studio (IDE). В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), соединиться с базой данных из **обозреватель объектов SQL Server**, или создайте подключение данных к базе данных в **обозревателя серверов**. Эти панели обозревателя из **представление** меню.
  
## <a name="see-also"></a>См. также

- [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
