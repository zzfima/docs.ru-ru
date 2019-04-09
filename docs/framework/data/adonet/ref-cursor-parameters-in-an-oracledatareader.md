---
title: Параметры REF CURSOR в объекте OracleDataReader
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 801dff0f-2508-45aa-9416-f45d6887740c
ms.openlocfilehash: 0c949f0d1ed43b66f72afc4059014c92293f3d75
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121853"
---
# <a name="ref-cursor-parameters-in-an-oracledatareader"></a><span data-ttu-id="73708-102">Параметры REF CURSOR в объекте OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="73708-102">REF CURSOR Parameters in an OracleDataReader</span></span>
<span data-ttu-id="73708-103">Этот пример на языке Microsoft Visual Basic выполняет хранимую процедуру PL/SQL, возвращающую параметр REF CURSOR, и считывает значение в виде <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="73708-103">This Microsoft Visual Basic example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
```vb  
Private Sub Button1_Click(ByVal sender As Object, _  
  ByVal e As System.EventArgs) Handles Button1.Click  
  
  Dim connString As New String(_  
      "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
    Dim rdr As OracleDataReader  
  
    conn.Open()  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_ONE_CURSOR"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter(  
      "N_EMPNO", OracleType.Number)).Value = 7369  
    cmd.Parameters.Add(New OracleParameter(  
      "IO_CURSOR", OracleType.Cursor)).Direction = ParameterDirection.Output  
  
    rdr = cmd.ExecuteReader()  
    While (rdr.Read())  
        REM do something with the values  
    End While  
  
    rdr.Close()  
  End Using  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="73708-104">См. также</span><span class="sxs-lookup"><span data-stu-id="73708-104">See also</span></span>

- [<span data-ttu-id="73708-105">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="73708-105">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)
- [<span data-ttu-id="73708-106">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="73708-106">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
