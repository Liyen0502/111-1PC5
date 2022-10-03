# 111-1PC5
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.UI;
using System.Web.UI.WebControls;

namespace _111_1PC5
{
    public partial class WebForm1 : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            int[] ia_Money = int[19]{
                10000, 36, 720, 360, 80, 
                252, 108, 72, 54, 180,
                72, 180, 119, 36, 306, 
                1080, 144, 1800, 3600
            };

            int[,] ia_2DArr = new int[3, 3]
            {
                { 7, 8, 9  },
                { 1, 4, 3  },
                { 2, 5, 6  },
            };

            mt_Getmost(ia_2DArr, ia_Money);
        }




        int mt_GetMost(int[,] ia_2DArr, int[] ia_Money)
        {
            int i_MaxMoney = 0;
            int i_MaxSum = 0;

            for (int i_Row=0; i_Row < ia_2DArr.GetLength(0); i_Row++)
            {
                int i_CalulatingSum = 0;
                int i_TmpMaxMoney = 0;
                for (int i_Col=0; i_Col < ia_2DArr.GetLength(1); i_Col++)
                {
                    i_CalulatingSum += ia_2DArr[i_Row, i_Col];
                }
                i_TmpMaxMoney = ia_Money[(i_CalulatingSum - 6)];
                if (i_TmpMaxMoney > i_MaxMoney)
                {
                    i_MaxMoney = i_CalulatingSum;
                }
            }
        }
    }
}
