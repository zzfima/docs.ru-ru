---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750013"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="af3e5-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="af3e5-102">ODBC Schema Collections</span></span>
<span data-ttu-id="af3e5-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="af3e5-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="af3e5-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="af3e5-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="af3e5-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="af3e5-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="af3e5-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="af3e5-106">Tables</span></span>  
  
-   <span data-ttu-id="af3e5-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="af3e5-107">Indexes</span></span>  
  
-   <span data-ttu-id="af3e5-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-108">Columns</span></span>  
  
-   <span data-ttu-id="af3e5-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-109">Procedures</span></span>  
  
-   <span data-ttu-id="af3e5-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="af3e5-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="af3e5-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="af3e5-112">Представления</span><span class="sxs-lookup"><span data-stu-id="af3e5-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="af3e5-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="af3e5-113">Tables and Views</span></span>  
  
|<span data-ttu-id="af3e5-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-114">ColumnName</span></span>|<span data-ttu-id="af3e5-115">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-116">TABLE_CAT</span></span>|<span data-ttu-id="af3e5-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-117">String</span></span>|  
|<span data-ttu-id="af3e5-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-118">TABLE_SCHEM</span></span>|<span data-ttu-id="af3e5-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-119">String</span></span>|  
|<span data-ttu-id="af3e5-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-120">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-121">String</span></span>|  
|<span data-ttu-id="af3e5-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-122">TABLE_TYPE</span></span>|<span data-ttu-id="af3e5-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-123">String</span></span>|  
|<span data-ttu-id="af3e5-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-124">REMARKS</span></span>|<span data-ttu-id="af3e5-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="af3e5-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="af3e5-126">Indexes</span></span>  
  
|<span data-ttu-id="af3e5-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-127">ColumnName</span></span>|<span data-ttu-id="af3e5-128">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-129">TABLE_CAT</span></span>|<span data-ttu-id="af3e5-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-130">String</span></span>|  
|<span data-ttu-id="af3e5-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-131">TABLE_SCHEM</span></span>|<span data-ttu-id="af3e5-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-132">String</span></span>|  
|<span data-ttu-id="af3e5-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-133">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-134">String</span></span>|  
|<span data-ttu-id="af3e5-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="af3e5-135">NON_UNIQUE</span></span>|<span data-ttu-id="af3e5-136">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-136">Int16</span></span>|  
|<span data-ttu-id="af3e5-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="af3e5-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-138">String</span></span>|  
|<span data-ttu-id="af3e5-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-139">INDEX_NAME</span></span>|<span data-ttu-id="af3e5-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-140">String</span></span>|  
|<span data-ttu-id="af3e5-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-141">TYPE</span></span>|<span data-ttu-id="af3e5-142">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-142">Int16</span></span>|  
|<span data-ttu-id="af3e5-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-144">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-144">Int16</span></span>|  
|<span data-ttu-id="af3e5-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-145">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-146">String</span></span>|  
|<span data-ttu-id="af3e5-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="af3e5-147">ASC_OR_DESC</span></span>|<span data-ttu-id="af3e5-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-148">String</span></span>|  
|<span data-ttu-id="af3e5-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="af3e5-149">CARDINATLITY</span></span>|<span data-ttu-id="af3e5-150">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-150">Int32</span></span>|  
|<span data-ttu-id="af3e5-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="af3e5-151">PAGES</span></span>|<span data-ttu-id="af3e5-152">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-152">Int32</span></span>|  
|<span data-ttu-id="af3e5-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-153">FILTER_CONDITION</span></span>|<span data-ttu-id="af3e5-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-154">String</span></span>|  
|<span data-ttu-id="af3e5-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="af3e5-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="af3e5-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-156">String</span></span>|  
|<span data-ttu-id="af3e5-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-158">Byte</span><span class="sxs-lookup"><span data-stu-id="af3e5-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="af3e5-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-159">Columns</span></span>  
  
|<span data-ttu-id="af3e5-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-160">ColumnName</span></span>|<span data-ttu-id="af3e5-161">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-162">TABLE_CAT</span></span>|<span data-ttu-id="af3e5-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-163">String</span></span>|  
|<span data-ttu-id="af3e5-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-164">TABLE_SCHEM</span></span>|<span data-ttu-id="af3e5-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-165">String</span></span>|  
|<span data-ttu-id="af3e5-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-166">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-167">String</span></span>|  
|<span data-ttu-id="af3e5-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-168">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-169">String</span></span>|  
|<span data-ttu-id="af3e5-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-170">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-171">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-171">Int16</span></span>|  
|<span data-ttu-id="af3e5-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-172">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-173">String</span></span>|  
|<span data-ttu-id="af3e5-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="af3e5-174">COLUMN_SIZE</span></span>|<span data-ttu-id="af3e5-175">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-175">Int32</span></span>|  
|<span data-ttu-id="af3e5-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="af3e5-177">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-177">Int32</span></span>|  
|<span data-ttu-id="af3e5-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="af3e5-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="af3e5-179">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-179">Int16</span></span>|  
|<span data-ttu-id="af3e5-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="af3e5-181">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-181">Int16</span></span>|  
|<span data-ttu-id="af3e5-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-182">NULLABLE</span></span>|<span data-ttu-id="af3e5-183">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-183">Int16</span></span>|  
|<span data-ttu-id="af3e5-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-184">REMARKS</span></span>|<span data-ttu-id="af3e5-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-185">String</span></span>|  
|<span data-ttu-id="af3e5-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="af3e5-186">COLUMN_DEF</span></span>|<span data-ttu-id="af3e5-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-187">String</span></span>|  
|<span data-ttu-id="af3e5-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-189">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-189">Int16</span></span>|  
|<span data-ttu-id="af3e5-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="af3e5-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="af3e5-191">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-191">Int16</span></span>|  
|<span data-ttu-id="af3e5-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="af3e5-193">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-193">Int32</span></span>|  
|<span data-ttu-id="af3e5-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-195">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-195">Int32</span></span>|  
|<span data-ttu-id="af3e5-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-196">IS_NULLABLE</span></span>|<span data-ttu-id="af3e5-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-197">String</span></span>|  
|<span data-ttu-id="af3e5-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="af3e5-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="af3e5-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-199">String</span></span>|  
|<span data-ttu-id="af3e5-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="af3e5-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="af3e5-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-201">String</span></span>|  
|<span data-ttu-id="af3e5-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-203">Byte</span><span class="sxs-lookup"><span data-stu-id="af3e5-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="af3e5-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-204">Procedures</span></span>  
  
|<span data-ttu-id="af3e5-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-205">ColumnName</span></span>|<span data-ttu-id="af3e5-206">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="af3e5-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-208">String</span></span>|  
|<span data-ttu-id="af3e5-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="af3e5-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-210">String</span></span>|  
|<span data-ttu-id="af3e5-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-212">String</span></span>|  
|<span data-ttu-id="af3e5-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-214">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-214">Int32</span></span>|  
|<span data-ttu-id="af3e5-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-216">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-216">Int32</span></span>|  
|<span data-ttu-id="af3e5-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="af3e5-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="af3e5-218">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-218">Int32</span></span>|  
|<span data-ttu-id="af3e5-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-219">REMARKS</span></span>|<span data-ttu-id="af3e5-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-220">String</span></span>|  
|<span data-ttu-id="af3e5-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="af3e5-222">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="af3e5-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="af3e5-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-224">ColumnName</span></span>|<span data-ttu-id="af3e5-225">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="af3e5-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-227">String</span></span>|  
|<span data-ttu-id="af3e5-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="af3e5-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-229">String</span></span>|  
|<span data-ttu-id="af3e5-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-231">String</span></span>|  
|<span data-ttu-id="af3e5-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-232">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-233">String</span></span>|  
|<span data-ttu-id="af3e5-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-234">COLUMN_TYPE</span></span>|<span data-ttu-id="af3e5-235">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-235">Int16</span></span>|  
|<span data-ttu-id="af3e5-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-236">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-237">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-237">Int16</span></span>|  
|<span data-ttu-id="af3e5-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-238">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-239">String</span></span>|  
|<span data-ttu-id="af3e5-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="af3e5-240">COLUMN_SIZE</span></span>|<span data-ttu-id="af3e5-241">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-241">Int32</span></span>|  
|<span data-ttu-id="af3e5-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="af3e5-243">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-243">Int32</span></span>|  
|<span data-ttu-id="af3e5-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="af3e5-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="af3e5-245">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-245">Int16</span></span>|  
|<span data-ttu-id="af3e5-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="af3e5-247">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-247">Int16</span></span>|  
|<span data-ttu-id="af3e5-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-248">NULLABLE</span></span>|<span data-ttu-id="af3e5-249">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-249">Int16</span></span>|  
|<span data-ttu-id="af3e5-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-250">REMARKS</span></span>|<span data-ttu-id="af3e5-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-251">String</span></span>|  
|<span data-ttu-id="af3e5-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="af3e5-252">COLUMN_DEF</span></span>|<span data-ttu-id="af3e5-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-253">String</span></span>|  
|<span data-ttu-id="af3e5-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-255">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-255">Int16</span></span>|  
|<span data-ttu-id="af3e5-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="af3e5-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="af3e5-257">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-257">Int16</span></span>|  
|<span data-ttu-id="af3e5-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="af3e5-259">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-259">Int32</span></span>|  
|<span data-ttu-id="af3e5-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-261">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-261">Int32</span></span>|  
|<span data-ttu-id="af3e5-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-262">IS_NULLABLE</span></span>|<span data-ttu-id="af3e5-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-263">String</span></span>|  
|<span data-ttu-id="af3e5-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="af3e5-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="af3e5-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-265">String</span></span>|  
|<span data-ttu-id="af3e5-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="af3e5-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="af3e5-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-267">String</span></span>|  
|<span data-ttu-id="af3e5-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-269">Byte</span><span class="sxs-lookup"><span data-stu-id="af3e5-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="af3e5-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="af3e5-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="af3e5-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-271">ColumnName</span></span>|<span data-ttu-id="af3e5-272">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="af3e5-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-274">String</span></span>|  
|<span data-ttu-id="af3e5-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="af3e5-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-276">String</span></span>|  
|<span data-ttu-id="af3e5-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-278">String</span></span>|  
|<span data-ttu-id="af3e5-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-279">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-280">String</span></span>|  
|<span data-ttu-id="af3e5-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-281">COLUMN_TYPE</span></span>|<span data-ttu-id="af3e5-282">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-282">Int16</span></span>|  
|<span data-ttu-id="af3e5-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-283">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-284">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-284">Int16</span></span>|  
|<span data-ttu-id="af3e5-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-285">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-286">String</span></span>|  
|<span data-ttu-id="af3e5-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="af3e5-287">COLUMN_SIZE</span></span>|<span data-ttu-id="af3e5-288">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-288">Int32</span></span>|  
|<span data-ttu-id="af3e5-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="af3e5-290">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-290">Int32</span></span>|  
|<span data-ttu-id="af3e5-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="af3e5-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="af3e5-292">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-292">Int16</span></span>|  
|<span data-ttu-id="af3e5-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="af3e5-294">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-294">Int16</span></span>|  
|<span data-ttu-id="af3e5-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-295">NULLABLE</span></span>|<span data-ttu-id="af3e5-296">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-296">Int16</span></span>|  
|<span data-ttu-id="af3e5-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-297">REMARKS</span></span>|<span data-ttu-id="af3e5-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-298">String</span></span>|  
|<span data-ttu-id="af3e5-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="af3e5-299">COLUMN_DEF</span></span>|<span data-ttu-id="af3e5-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-300">String</span></span>|  
|<span data-ttu-id="af3e5-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-302">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-302">Int16</span></span>|  
|<span data-ttu-id="af3e5-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="af3e5-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="af3e5-304">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-304">Int16</span></span>|  
|<span data-ttu-id="af3e5-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="af3e5-306">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-306">Int32</span></span>|  
|<span data-ttu-id="af3e5-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-308">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-308">Int32</span></span>|  
|<span data-ttu-id="af3e5-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-309">IS_NULLABLE</span></span>|<span data-ttu-id="af3e5-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-310">String</span></span>|  
|<span data-ttu-id="af3e5-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="af3e5-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="af3e5-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-312">String</span></span>|  
|<span data-ttu-id="af3e5-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="af3e5-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="af3e5-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-314">String</span></span>|  
|<span data-ttu-id="af3e5-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-316">Byte</span><span class="sxs-lookup"><span data-stu-id="af3e5-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="af3e5-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="af3e5-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="af3e5-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="af3e5-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="af3e5-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="af3e5-319">Tables</span></span>  
  
-   <span data-ttu-id="af3e5-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-320">Columns</span></span>  
  
-   <span data-ttu-id="af3e5-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-321">Procedures</span></span>  
  
-   <span data-ttu-id="af3e5-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="af3e5-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="af3e5-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="af3e5-324">Представления</span><span class="sxs-lookup"><span data-stu-id="af3e5-324">Views</span></span>  
  
-   <span data-ttu-id="af3e5-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="af3e5-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="af3e5-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="af3e5-326">Tables and Views</span></span>  
  
|<span data-ttu-id="af3e5-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-327">ColumnName</span></span>|<span data-ttu-id="af3e5-328">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-330">String</span></span>|  
|<span data-ttu-id="af3e5-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-331">TABLE_OWNER</span></span>|<span data-ttu-id="af3e5-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-332">String</span></span>|  
|<span data-ttu-id="af3e5-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-333">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-334">String</span></span>|  
|<span data-ttu-id="af3e5-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-335">TABLE_TYPE</span></span>|<span data-ttu-id="af3e5-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-336">String</span></span>|  
|<span data-ttu-id="af3e5-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-337">REMARKS</span></span>|<span data-ttu-id="af3e5-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="af3e5-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-339">Columns</span></span>  
  
|<span data-ttu-id="af3e5-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-340">ColumnName</span></span>|<span data-ttu-id="af3e5-341">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-343">String</span></span>|  
|<span data-ttu-id="af3e5-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-344">TABLE_OWNER</span></span>|<span data-ttu-id="af3e5-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-345">String</span></span>|  
|<span data-ttu-id="af3e5-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-346">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-347">String</span></span>|  
|<span data-ttu-id="af3e5-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-348">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-349">String</span></span>|  
|<span data-ttu-id="af3e5-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-350">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-351">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-351">Int16</span></span>|  
|<span data-ttu-id="af3e5-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-352">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-353">String</span></span>|  
|<span data-ttu-id="af3e5-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="af3e5-354">PRECISION</span></span>|<span data-ttu-id="af3e5-355">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-355">Int32</span></span>|  
|<span data-ttu-id="af3e5-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-356">LENGTH</span></span>|<span data-ttu-id="af3e5-357">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-357">Int32</span></span>|  
|<span data-ttu-id="af3e5-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="af3e5-358">SCALE</span></span>|<span data-ttu-id="af3e5-359">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-359">Int16</span></span>|  
|<span data-ttu-id="af3e5-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-360">RADIX</span></span>|<span data-ttu-id="af3e5-361">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-361">Int16</span></span>|  
|<span data-ttu-id="af3e5-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-362">NULLABLE</span></span>|<span data-ttu-id="af3e5-363">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-363">Int16</span></span>|  
|<span data-ttu-id="af3e5-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-364">REMARKS</span></span>|<span data-ttu-id="af3e5-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-365">String</span></span>|  
|<span data-ttu-id="af3e5-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-367">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="af3e5-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-368">Procedures</span></span>  
  
|<span data-ttu-id="af3e5-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-369">ColumnName</span></span>|<span data-ttu-id="af3e5-370">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-372">String</span></span>|  
|<span data-ttu-id="af3e5-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="af3e5-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-374">String</span></span>|  
|<span data-ttu-id="af3e5-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-376">String</span></span>|  
|<span data-ttu-id="af3e5-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-378">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-378">Int16</span></span>|  
|<span data-ttu-id="af3e5-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-380">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-380">Int16</span></span>|  
|<span data-ttu-id="af3e5-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="af3e5-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="af3e5-382">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-382">Int16</span></span>|  
|<span data-ttu-id="af3e5-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-383">REMARKS</span></span>|<span data-ttu-id="af3e5-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-384">String</span></span>|  
|<span data-ttu-id="af3e5-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="af3e5-386">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="af3e5-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="af3e5-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-388">ColumnName</span></span>|<span data-ttu-id="af3e5-389">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-391">String</span></span>|  
|<span data-ttu-id="af3e5-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="af3e5-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-393">String</span></span>|  
|<span data-ttu-id="af3e5-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-395">String</span></span>|  
|<span data-ttu-id="af3e5-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-396">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-397">String</span></span>|  
|<span data-ttu-id="af3e5-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-398">COLUMN_TYPE</span></span>|<span data-ttu-id="af3e5-399">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-399">Int16</span></span>|  
|<span data-ttu-id="af3e5-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-400">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-401">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-401">Int16</span></span>|  
|<span data-ttu-id="af3e5-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-402">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-403">String</span></span>|  
|<span data-ttu-id="af3e5-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="af3e5-404">PRECISION</span></span>|<span data-ttu-id="af3e5-405">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-405">Int32</span></span>|  
|<span data-ttu-id="af3e5-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-406">LENGTH</span></span>|<span data-ttu-id="af3e5-407">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-407">Int32</span></span>|  
|<span data-ttu-id="af3e5-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="af3e5-408">SCALE</span></span>|<span data-ttu-id="af3e5-409">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-409">Int16</span></span>|  
|<span data-ttu-id="af3e5-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-410">RADIX</span></span>|<span data-ttu-id="af3e5-411">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-411">Int16</span></span>|  
|<span data-ttu-id="af3e5-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-412">NULLABLE</span></span>|<span data-ttu-id="af3e5-413">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-413">Int16</span></span>|  
|<span data-ttu-id="af3e5-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-414">REMARKS</span></span>|<span data-ttu-id="af3e5-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-415">String</span></span>|  
|<span data-ttu-id="af3e5-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="af3e5-416">OVERLOAD</span></span>|<span data-ttu-id="af3e5-417">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-417">Int32</span></span>|  
|<span data-ttu-id="af3e5-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-419">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="af3e5-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="af3e5-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="af3e5-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="af3e5-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="af3e5-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="af3e5-422">Tables</span></span>  
  
-   <span data-ttu-id="af3e5-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="af3e5-423">Indexes</span></span>  
  
-   <span data-ttu-id="af3e5-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-424">Columns</span></span>  
  
-   <span data-ttu-id="af3e5-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-425">Procedures</span></span>  
  
-   <span data-ttu-id="af3e5-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="af3e5-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="af3e5-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="af3e5-428">Представления</span><span class="sxs-lookup"><span data-stu-id="af3e5-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="af3e5-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="af3e5-429">Tables and Views</span></span>  
  
|<span data-ttu-id="af3e5-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-430">ColumnName</span></span>|<span data-ttu-id="af3e5-431">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-433">String</span></span>|  
|<span data-ttu-id="af3e5-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-434">TABLE_OWNER</span></span>|<span data-ttu-id="af3e5-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-435">String</span></span>|  
|<span data-ttu-id="af3e5-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-436">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-437">String</span></span>|  
|<span data-ttu-id="af3e5-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-438">TABLE_TYPE</span></span>|<span data-ttu-id="af3e5-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-439">String</span></span>|  
|<span data-ttu-id="af3e5-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-440">REMARKS</span></span>|<span data-ttu-id="af3e5-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="af3e5-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="af3e5-442">Columns</span></span>  
  
|<span data-ttu-id="af3e5-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-443">ColumnName</span></span>|<span data-ttu-id="af3e5-444">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-446">String</span></span>|  
|<span data-ttu-id="af3e5-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-447">TABLE_OWNER</span></span>|<span data-ttu-id="af3e5-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-448">String</span></span>|  
|<span data-ttu-id="af3e5-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-449">TABLE_NAME</span></span>|<span data-ttu-id="af3e5-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-450">String</span></span>|  
|<span data-ttu-id="af3e5-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-451">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-452">String</span></span>|  
|<span data-ttu-id="af3e5-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-453">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-454">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-454">Int16</span></span>|  
|<span data-ttu-id="af3e5-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-455">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-456">String</span></span>|  
|<span data-ttu-id="af3e5-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="af3e5-457">PRECISION</span></span>|<span data-ttu-id="af3e5-458">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-458">Int32</span></span>|  
|<span data-ttu-id="af3e5-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-459">LENGTH</span></span>|<span data-ttu-id="af3e5-460">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-460">Int32</span></span>|  
|<span data-ttu-id="af3e5-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="af3e5-461">SCALE</span></span>|<span data-ttu-id="af3e5-462">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-462">Int16</span></span>|  
|<span data-ttu-id="af3e5-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-463">RADIX</span></span>|<span data-ttu-id="af3e5-464">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-464">Int16</span></span>|  
|<span data-ttu-id="af3e5-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-465">NULLABLE</span></span>|<span data-ttu-id="af3e5-466">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-466">Int16</span></span>|  
|<span data-ttu-id="af3e5-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-467">REMARKS</span></span>|<span data-ttu-id="af3e5-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-468">String</span></span>|  
|<span data-ttu-id="af3e5-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-470">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="af3e5-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="af3e5-471">Procedures</span></span>  
  
|<span data-ttu-id="af3e5-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-472">ColumnName</span></span>|<span data-ttu-id="af3e5-473">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-475">String</span></span>|  
|<span data-ttu-id="af3e5-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="af3e5-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-477">String</span></span>|  
|<span data-ttu-id="af3e5-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-479">String</span></span>|  
|<span data-ttu-id="af3e5-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-481">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-481">Int16</span></span>|  
|<span data-ttu-id="af3e5-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="af3e5-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="af3e5-483">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-483">Int16</span></span>|  
|<span data-ttu-id="af3e5-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="af3e5-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="af3e5-485">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-485">Int16</span></span>|  
|<span data-ttu-id="af3e5-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-486">REMARKS</span></span>|<span data-ttu-id="af3e5-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-487">String</span></span>|  
|<span data-ttu-id="af3e5-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="af3e5-489">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="af3e5-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="af3e5-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="af3e5-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-491">ColumnName</span></span>|<span data-ttu-id="af3e5-492">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="af3e5-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="af3e5-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-494">String</span></span>|  
|<span data-ttu-id="af3e5-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3e5-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="af3e5-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-496">String</span></span>|  
|<span data-ttu-id="af3e5-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-498">String</span></span>|  
|<span data-ttu-id="af3e5-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-499">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-500">String</span></span>|  
|<span data-ttu-id="af3e5-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-501">COLUMN_TYPE</span></span>|<span data-ttu-id="af3e5-502">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-502">Int16</span></span>|  
|<span data-ttu-id="af3e5-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-503">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-504">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-504">Int16</span></span>|  
|<span data-ttu-id="af3e5-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-505">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-506">String</span></span>|  
|<span data-ttu-id="af3e5-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="af3e5-507">PRECISION</span></span>|<span data-ttu-id="af3e5-508">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-508">Int32</span></span>|  
|<span data-ttu-id="af3e5-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-509">LENGTH</span></span>|<span data-ttu-id="af3e5-510">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-510">Int32</span></span>|  
|<span data-ttu-id="af3e5-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="af3e5-511">SCALE</span></span>|<span data-ttu-id="af3e5-512">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-512">Int16</span></span>|  
|<span data-ttu-id="af3e5-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-513">RADIX</span></span>|<span data-ttu-id="af3e5-514">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-514">Int16</span></span>|  
|<span data-ttu-id="af3e5-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-515">NULLABLE</span></span>|<span data-ttu-id="af3e5-516">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-516">Int16</span></span>|  
|<span data-ttu-id="af3e5-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-517">REMARKS</span></span>|<span data-ttu-id="af3e5-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-518">String</span></span>|  
|<span data-ttu-id="af3e5-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="af3e5-519">OVERLOAD</span></span>|<span data-ttu-id="af3e5-520">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-520">Int32</span></span>|  
|<span data-ttu-id="af3e5-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-522">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="af3e5-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="af3e5-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="af3e5-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="af3e5-524">ColumnName</span></span>|<span data-ttu-id="af3e5-525">DataType</span><span class="sxs-lookup"><span data-stu-id="af3e5-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="af3e5-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="af3e5-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="af3e5-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-527">String</span></span>|  
|<span data-ttu-id="af3e5-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="af3e5-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="af3e5-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-529">String</span></span>|  
|<span data-ttu-id="af3e5-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="af3e5-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-531">String</span></span>|  
|<span data-ttu-id="af3e5-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-532">COLUMN_NAME</span></span>|<span data-ttu-id="af3e5-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-533">String</span></span>|  
|<span data-ttu-id="af3e5-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-534">COLUMN_TYPE</span></span>|<span data-ttu-id="af3e5-535">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-535">Int16</span></span>|  
|<span data-ttu-id="af3e5-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-536">DATA_TYPE</span></span>|<span data-ttu-id="af3e5-537">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-537">Int16</span></span>|  
|<span data-ttu-id="af3e5-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="af3e5-538">TYPE_NAME</span></span>|<span data-ttu-id="af3e5-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-539">String</span></span>|  
|<span data-ttu-id="af3e5-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="af3e5-540">COLUMN_SIZE</span></span>|<span data-ttu-id="af3e5-541">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-541">Int32</span></span>|  
|<span data-ttu-id="af3e5-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="af3e5-543">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-543">Int32</span></span>|  
|<span data-ttu-id="af3e5-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="af3e5-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="af3e5-545">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-545">Int16</span></span>|  
|<span data-ttu-id="af3e5-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="af3e5-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="af3e5-547">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-547">Int16</span></span>|  
|<span data-ttu-id="af3e5-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-548">NULLABLE</span></span>|<span data-ttu-id="af3e5-549">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-549">Int16</span></span>|  
|<span data-ttu-id="af3e5-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="af3e5-550">REMARKS</span></span>|<span data-ttu-id="af3e5-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-551">String</span></span>|  
|<span data-ttu-id="af3e5-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="af3e5-552">COLUMN_DEF</span></span>|<span data-ttu-id="af3e5-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="af3e5-553">String</span></span>|  
|<span data-ttu-id="af3e5-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="af3e5-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="af3e5-555">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-555">Int16</span></span>|  
|<span data-ttu-id="af3e5-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="af3e5-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="af3e5-557">Int16</span><span class="sxs-lookup"><span data-stu-id="af3e5-557">Int16</span></span>|  
|<span data-ttu-id="af3e5-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="af3e5-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="af3e5-559">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-559">Int32</span></span>|  
|<span data-ttu-id="af3e5-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="af3e5-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="af3e5-561">Int32</span><span class="sxs-lookup"><span data-stu-id="af3e5-561">Int32</span></span>|  
|<span data-ttu-id="af3e5-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="af3e5-562">IS_NULLABLE</span></span>|<span data-ttu-id="af3e5-563">String</span><span class="sxs-lookup"><span data-stu-id="af3e5-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af3e5-564">См. также</span><span class="sxs-lookup"><span data-stu-id="af3e5-564">See Also</span></span>  
 [<span data-ttu-id="af3e5-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="af3e5-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
