---
title: Примеры REF CURSOR
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: dc82648ff5a565c9b4d6fa593433ee1e22249d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149139"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="a7cc4-102">Примеры REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="a7cc4-102">REF CURSOR Examples</span></span>
<span data-ttu-id="a7cc4-103">Примеры REF CURSOR состоят из трех следующих примеров Microsoft Visual Basic, в которых демонстрируется использование REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="a7cc4-104">Образец</span><span class="sxs-lookup"><span data-stu-id="a7cc4-104">Sample</span></span>|<span data-ttu-id="a7cc4-105">Описание</span><span class="sxs-lookup"><span data-stu-id="a7cc4-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7cc4-106">Параметры REF CURSOR в объекте OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="a7cc4-106">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="a7cc4-107">В этом примере выполняется хранимая процедура PL/SQL, которая возвращает параметр REF CURSOR и считывает значение через <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="a7cc4-108">Извлечение данных нескольких REF CURSOR с использованием OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="a7cc4-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="a7cc4-109">Этот пример выполняет процедуру хранения PL/S'L, которая возвращает два параметра REF CURSOR и считывает значения с помощью **OracleDataReader.**</span><span class="sxs-lookup"><span data-stu-id="a7cc4-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="a7cc4-110">Заполнение набора данных с помощью одного или нескольких параметров REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="a7cc4-110">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="a7cc4-111">В этом примере выполняется хранимая процедура PL/SQL, которая возвращает два параметра REF CURSOR и заполняет набор <xref:System.Data.DataSet> возвращенными строками.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="a7cc4-112">Чтобы использовать эти примеры, может потребоваться создать таблицы Oracle; кроме того, необходимо создать пакет и текст пакета PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="a7cc4-113">Создание таблиц Oracle</span><span class="sxs-lookup"><span data-stu-id="a7cc4-113">Creating the Oracle Tables</span></span>  
 <span data-ttu-id="a7cc4-114">В этих примерах используются таблицы, которые определены в схеме Oracle Scott/Tiger.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="a7cc4-115">Схема Oracle Scott/Tiger имеется в большинстве установок Oracle.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="a7cc4-116">Если этой схемы не существует, чтобы создать таблицы и индексы для этих примеров, можно использовать командный файл SQL в {OracleHome}\rdbms\admin\scott.sql.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="a7cc4-117">Создание пакета и текста пакета Oracle</span><span class="sxs-lookup"><span data-stu-id="a7cc4-117">Creating the Oracle Package and Package Body</span></span>  
 <span data-ttu-id="a7cc4-118">Для этих примеров требуется наличие на вашем сервере следующих пакетов и текста пакета PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="a7cc4-119">Создайте на сервере Oracle следующий пакет Oracle.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
    TYPE T_CURSOR IS REF CURSOR;
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,
                               IO_CURSOR IN OUT T_CURSOR);
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/
```  
  
 <span data-ttu-id="a7cc4-120">На сервере Oracle создайте следующий текст пакета Oracle.</span><span class="sxs-lookup"><span data-stu-id="a7cc4-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS
        V_CURSOR T_CURSOR;
    BEGIN
        IF N_EMPNO <> 0
        THEN  
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;
    END OPEN_ONE_CURSOR;
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS
        V_CURSOR1 T_CURSOR;
        V_CURSOR2 T_CURSOR;
    BEGIN
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;
        DEPTCURSOR := V_CURSOR2;
    END OPEN_TWO_CURSORS;
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7cc4-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7cc4-121">See also</span></span>

- [<span data-ttu-id="a7cc4-122">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="a7cc4-122">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)
- [<span data-ttu-id="a7cc4-123">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a7cc4-123">ADO.NET Overview</span></span>](ado-net-overview.md)
