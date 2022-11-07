# 第3次作業-作業-HW3
>
>學號：109111101
><br />
>姓名：邱韋翔
><br />
>作業撰寫時間：180 (mins，包含程式撰寫時間)
><br />
>最後撰寫文件日期：2022/11/7
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x]說明內容
- [x]個人認為完成作業須具備觀念

## 說明程式與內容

下段程式碼則為使用後結果：

```html
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Test.aspx.cs" Inherits="_111_1HW3.Test" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <asp:DropDownList ID="ddl_Category" runat="server" OnSelectedIndexChanged="ddl_Category_SelectedIndexChanged" AutoPostBack="True" ></asp:DropDownList>
            <asp:DropDownList ID="ddl_Food" runat="server"></asp:DropDownList>
        </div>
    </form>
</body>
</html>
```

```csharp
public partial class Test : System.Web.UI.Page
    {
        string[] sa_Cat = new string[2] {"蔬菜","水果"};
        string[,] sa_2D = new string[2,2] { {"A菜", "空心菜"}, {"番茄","火龍果" } };
        protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                for (int i_Ct = 0; i_Ct < sa_Cat.Length; i_Ct++)
                {
                    ListItem o_L = new ListItem();
                    o_L.Text = o_L.Value = sa_Cat[i_Ct];

                    ddl_Category.Items.Add(o_L);
                }
                mt_GenSecondList();
            }
        }
        protected void ddl_Category_SelectedIndexChanged(object sender, EventArgs e)
        {

            mt_GenSecondList();
        }

        protected void mt_GenSecondList()
        {
            int i_ind = ddl_Category.SelectedIndex;
            ddl_Food.Items.Clear();
            for (int i_Ct = 0;i_Ct< sa_2D.GetLength(1); i_Ct++)//sa_2D.GetLength(1)是抓取sa_2D[(0),(1)]
            {
                ListItem o_L = new ListItem();
                o_L.Text = o_L.Value = sa_2D[i_ind,i_Ct];

                ddl_Food.Items.Add(o_L);
            }
            //Response.Write(ddl_Category.SelectedIndex);
        }
    }
}
```


## 個人認為完成作業須具備觀念

開始寫說明，需要說明本次作業個人覺得需學會那些觀念 (需寫成文章，需最少50字，
並且文內不得有你、我、他三種文字)

