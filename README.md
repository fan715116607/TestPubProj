# TestPubProj
import java.io.*;

import org.apache.poi.hslf.model.Sheet;
import org.apache.poi.hssf.usermodel.HSSFRow;
import org.apache.poi.hssf.usermodel.HSSFSheet;
import org.apache.poi.hssf.usermodel.HSSFWorkbook;
import org.apache.poi.poifs.filesystem.POIFSFileSystem;
/**
 * <p>
 * 这是写类描述，如果有换行则用<br>
 * </p>
 */
public class Test {

	public static void main(String[] args) throws Exception {
		// TODO Auto-generated method stub
		BufferedInputStream in = new BufferedInputStream(new FileInputStream(
				new File("c:/111.xls")));
		POIFSFileSystem fs = new POIFSFileSystem(in);
		HSSFWorkbook wb = new HSSFWorkbook(fs);
		HSSFSheet sheet = wb.getSheetAt(0);
		System.out.println(sheet.getLastRowNum());
		for (int i = 0; i < sheet.getLastRowNum(); i++) {
			HSSFRow hssfRow = sheet.getRow(i);
			for(int j =0;j<hssfRow.getLastCellNum();j++){
				System.out.print(hssfRow.getCell(j));
			}
			System.out.println();
		}
	}

}
