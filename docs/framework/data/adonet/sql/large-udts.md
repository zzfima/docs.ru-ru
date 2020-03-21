---
title: Большие UDT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: f55f6eccf3566a2391204e1ca4349ae5dff01954
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148560"
---
# <a name="large-udts"></a>Большие UDT
Определяемые пользователем типы призваны дать разработчику возможность расширить серверную систему скалярных типов путем хранения объектов среды CLR в базе данных SQL Server. Определяемые пользователем типы могут содержать несколько элементов, и их поведение может отличаться от традиционных псевдонимов типов данных, которые состоят из одного системного типа данных SQL Server.  
  
> [!NOTE]
> Чтобы воспользоваться расширенной поддержкой SqlClient определяемых пользователем типов данных большого размера, необходимо установить .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии.  
  
 Ранее размер определяемых пользователем типов был ограничен 8 килобайтами. Это ограничение было снято в SQL Server 2008 для определяемых пользователем типов, имеющих формат <xref:Microsoft.SqlServer.Server.Format.UserDefined>.  
  
 Полную документацию по определяемым пользователем типам данных см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Документация сервера S'L**  
  
1. [Определяемые пользователем типы CLR](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Загрузка схем определяемых пользователем типов данных с помощью метода GetSchema  
 Метод <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A><xref:System.Data.SqlClient.SqlConnection> возвращает сведения о схеме базы данных в <xref:System.Data.DataTable>. Для получения более подробной информации, [см.](../sql-server-schema-collections.md)  
  
### <a name="getschematable-column-values-for-udts"></a>Значения столбца GetSchemaTable для определяемых пользователем типов данных  
 Метод <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A><xref:System.Data.SqlClient.SqlDataReader> возвращает <xref:System.Data.DataTable>, описывающее метаданные столбца. В следующей таблице описаны различия в метаданных столбцов для больших пользовательских типов данных между SQL Server 2005 и SQL Server 2008.  
  
|Столбец SqlDataReader|SQL Server 2005|SQL Server 2008 и более поздние версии|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Различается|Различается|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|Экземпляр UDT|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|Экземпляр UDT|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Имя из трех частей, указанное как *Database.SchemaName.TypeName*.|  
|`IsLong`|Различается|Различается|  
  
## <a name="sqldatareader-considerations"></a>Вопросы, связанные с SqlDataReader  
 Объект <xref:System.Data.SqlClient.SqlDataReader> в SQL Server 2008 был расширен для поддержки загрузки значений определяемых пользователем типов данных большого размера. Как большие значения пользовательского типа обрабатываются <xref:System.Data.SqlClient.SqlDataReader>, зависит от используемой версии SQL Server, а также от `Type System Version`, указанного в строке подключения. Дополнительные сведения см. в разделе <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Следующие методы <xref:System.Data.SqlClient.SqlDataReader> будут возвращать <xref:System.Data.SqlTypes.SqlBinary> вместо пользовательского типа, если для `Type System Version` установлено значение SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 Следующие методы будут возвращать массив `Byte[]` вместо пользовательского типа, если для `Type System Version` установлено значение SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Обратите внимание, что для текущей версии ADO.NET никакие преобразования не выполняются.  
  
## <a name="specifying-sqlparameters"></a>Указание SqlParameters  
 Следующие свойства <xref:System.Data.SqlClient.SqlParameter> были расширены для работы с большими пользовательскими типами.  
  
|Свойство SqlParameter|Описание|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Возвращает или задает объект, представляющий значение параметра. Значение по умолчанию — NULL. Свойством может быть `SqlBinary`, `Byte[]` или управляемый объект.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Возвращает или задает объект, представляющий значение параметра. Значение по умолчанию — NULL. Свойством может быть `SqlBinary`, `Byte[]` или управляемый объект.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Возвращает или задает размер значения параметра для разрешения. Значение по умолчанию — 0. Свойство может быть целым числом, представляющим размер значения параметра. Для больших определяемых пользователем типов оно может равняться действительному размеру определяемого пользователем типа или иметь значение –1 — для неизвестных.|  
  
## <a name="retrieving-data-example"></a>Пример извлечения данных  
 В следующем фрагменте кода показано, как получить большие данные пользовательского типа. Переменная `connectionString` предполагает допустимое соединение с базой данных SQL Server, а переменная `commandString` предполагает, что допустимая инструкция SELECT со столбцом первичного ключа указана первой.  
  
```csharp  
using (SqlConnection connection = new SqlConnection(
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a>См. также раздел

- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Извлечение сведений о схеме базы данных](../retrieving-database-schema-information.md)
- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Двоичные и высокоценные данные сервера S'L](sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
