# GTN_world-Billing-Software
from tkinter import *
from tkinter import ttk
from PIL import Image, ImageTk
import random
from tkinter import messagebox
class Bill_App:
    def __init__(self, root):
        self.root =root
        self.root.geometry("1530x800+0+0")
        self.root.title("Billing Software")

        #=============variables==============se
        self.c_name=StringVar()
        self.c_phon = StringVar()
        self.bill_no = StringVar()
        z=random.randint(1000,9999)
        self.bill_no.set(z)
        self.c_email = StringVar()
        self.search_bill = StringVar()
        self.product = StringVar()
        self.prices = IntVar()
        self.qty = IntVar()
        self.sub_total = StringVar()
        self.tax_input = StringVar()
        self.total = StringVar()

        # #Product categories list
        self.Category=["Select Option","Clothing","lifestyle","Mobiles"]
        #clothing
        self.SubCatclothing=["Pant", "T-Shirt", "Shirt"]
        self.pant=["Levis","Mufti","Spykar"]
        self.price_levis=5000
        self.price_Mufti = 7000
        self.price_Skykar = 8000
        self.T_Shirt=["Polo","roadster","Jack&Jones"]
        self.price_Polo=1500
        self.price_roadster = 2700
        self.price_Jackjones = 1700
        self.Shirt=["Peter England","Louis Phillipe","Park Avenue"]
        self.price_Peter=2100
        self.price_Louis = 2700
        self.price_park = 1740
        #subcatlifestyle
        self.SubCatlifestyle=["Bath Soap", "Face Cream", "Hair Oil"]
        self.Bath_soap=["lifeBuy","Lux","Santoor","Pearl"]
        self.price_life=float(20)
        self.price_lux=20
        self.price_Santoor=20
        self.price_Pearl=20

        self.Face_cream=["Fair&lovely","Ponds","Olay","Garnier"]
        self.price_fair=20
        self.price_ponds=20
        self.price_olay=20
        self.price_garnier=20

        self.Hair_oil=["Parachute","Jashmin","Baja"]
        self.price_para=25
        self.price_ashmin=22
        self.price__bajaj=30

        #SubCatMobiles
        self.SubCatMobiles=["Iphone","Samsung","Nokia", "RealMe","OnePlus"]
        self.Iphone=["Iphone_X","Iphone_11","Iphone_12"]
        self.price_ix=180000
        self.price_i11=350000
        self.price_i12=480000

        self.Samsung=["Samsung S21","Samsung S22","Samsung S23","Samsung S24"]
        self.price_S21=540000
        self.price_S22 = 660000
        self.price_S23 = 780000
        self.price_S24 = 1200000

        self.Nokia=["Nokia C10","Nokia G10","Nokia G20"]
        self.price_C10 = 130000
        self.price_G10 = 186000
        self.price_G20 = 230000

        self.RealMe = ["RealMe 12", "RealMe 13", "RealMe Pro"]
        self.price_rel12 = 250000
        self.price_rel13 = 220000
        self.price_repro = 300000

        self.OnePlus=["OnePlus1","OnePlus2","OnePlus3"]
        self.price_one1=450000
        self.price_one2 = 600000
        self.price_one3 = 750000

        #Image 1
        img=Image.open("Images/Pic1.jpg")
        img=img.resize((500,130),Image.Resampling.LANCZOS)
        self.photoimg=ImageTk.PhotoImage(img)
        lb1_img=Label(self.root,image=self.photoimg)
        lb1_img.place(x=0,y=0,width=500,height=130)

        #Image 2
        img_1 = Image.open("Images/Pic2.jpg")
        img_1 = img_1.resize((500, 130), Image.Resampling.LANCZOS)
        self.photoimg_1 = ImageTk.PhotoImage(img_1)
        lb1_img_1 = Label(self.root, image=self.photoimg_1)
        lb1_img_1.place(x=500, y=0, width=500, height=130)

        #Image 3
        img_2 = Image.open("Images/Pic3.jpg")
        img_2 = img_2.resize((520, 130), Image.Resampling.LANCZOS)
        self.photoimg_2 = ImageTk.PhotoImage(img_2)
        lb1_img_2 = Label(self.root, image=self.photoimg_2)
        lb1_img_2.place(x=1000, y=0, width=520, height=130)
        lb1_title=Label(self.root,text="GTN World BILLING SOFTWARE",font=("times new roman",30,"bold"),bg="#740876",fg="#ff7f27")
        lb1_title.place(x=0,y=130,width=1530,height=45)

        Main_Frame=Frame(self.root,bd=5,relief=GROOVE,bg="white")
        Main_Frame.place(x=0,y=175,width=1530,height=620)

        # Customer LabelFrame
        cust_Frame=LabelFrame(Main_Frame,text="Customer",font=("times new roman",16,"bold"),bg="#740876",fg="#ff7f27")
        cust_Frame.place(x=10,y=5,width=350,height=140)

        self.lb1_mob=Label(cust_Frame,text="Mobile No.",font=("times new roman",12,"bold"),bg="#740876",fg="black")
        self.lb1_mob.grid(row=0,column=0,stick=W,padx=5,pady=2)

        self.entry_mob=ttk.Entry(cust_Frame,textvariable=self.c_phon,font=("times new roman",10,"bold"),width=24)
        self.entry_mob.grid(row=0,column=1)

        self.lb1CustName = Label(cust_Frame, text="Customer Name", font=("arial", 12, "bold"), bg="#740876",fg="black",bd=4)
        self.lb1CustName.grid(row=1, column=0, stick=W, padx=5, pady=2)

        self.txtCustName = ttk.Entry(cust_Frame,textvariable=self.c_name, font=("arial", 10, "bold"), width=24)
        self.txtCustName.grid(row=1, column=1,sticky=W,padx=5,pady=2)

        self.lb1Email = Label(cust_Frame, text="Email", font=("arial", 12, "bold"),bg="#740876",fg="black",bd=4)
        self.lb1Email.grid(row=2, column=0, stick=W, padx=5, pady=2)

        self.txtEmail = ttk.Entry(cust_Frame,textvariable=self.c_email ,font=("arial", 10, "bold"), width=24)
        self.txtEmail.grid(row=2, column=1,sticky=W,padx=5,pady=2)

        #Product LabelFrame
        Product_Frame = LabelFrame(Main_Frame, text="Product", font=("times new roman", 16, "bold"), bg="#740876",
                                fg="#ff7f27")
        Product_Frame.place(x=370, y=5, width=620, height=140)

        #Category
        self.lb1Category = Label(Product_Frame, text="Select Categories", font=("arial", 12, "bold"), bg="#740876",fg="black", bd=4)
        self.lb1Category.grid(row=0, column=0, stick=W, padx=5, pady=2)

        self.Combo_Category=ttk.Combobox(Product_Frame,value=self.Category,font=("arial", 10, "bold"), width=24,state="readonly")
        self.Combo_Category.current(0)
        self.Combo_Category.grid(row=0,column=1,sticky=W,padx=5,pady=2)
        self.Combo_Category.bind("<<ComboboxSelected>>",self.Categories)

        #SubCategory
        self.lb1SubCategory = Label(Product_Frame, text="SubCategory", font=("arial", 12, "bold"),bg="#740876",fg="black", bd=4)
        self.lb1SubCategory.grid(row=1, column=0, stick=W, padx=5, pady=2)

        self.ComboSubCategory = ttk.Combobox(Product_Frame, value=[""],font=("arial", 10, "bold"), width=24,state="readonly")
        self.ComboSubCategory.grid(row=1, column=1, sticky=W, padx=5, pady=2)
        self.ComboSubCategory.bind("<<ComboboxSelected>>",self.Product_add)

        #Product Name
        self.lb1product = Label(Product_Frame, text="Product Name", font=("arial", 12, "bold"),bg="#740876",fg="black", bd=4)
        self.lb1product.grid(row=2, column=0, stick=W, padx=5, pady=2)

        self.ComboProduct = ttk.Combobox(Product_Frame,textvariable=self.product, font=("arial", 10, "bold"), width=24, state="readonly")
        self.ComboProduct.grid(row=2, column=1, sticky=W, padx=5, pady=2)
        self.ComboProduct.bind("<<ComboboxSelected>>",self.price)

        #Price
        self.lb1price = Label(Product_Frame, text="Price", font=("arial", 12, "bold"),bg="#740876",fg="black", bd=4)
        self.lb1price.grid(row=0, column=2, stick=W, padx=5, pady=2)

        self.Comboprice = ttk.Combobox(Product_Frame, textvariable=self.prices,font=("arial", 10, "bold"), width=24, state="readonly")
        self.Comboprice.grid(row=0, column=3, sticky=W, padx=5, pady=2)

        #Quality
        self.lb1Qty = Label(Product_Frame, text="Qty", font=("arial", 12, "bold"),bg="#740876",fg="black", bd=4)
        self.lb1Qty.grid(row=1, column=2, stick=W, padx=5, pady=2)

        self.ComboQty = ttk.Entry(Product_Frame,textvariable=self.qty, font=("arial", 10, "bold"), width=26)
        self.ComboQty.grid(row=1, column=3, sticky=W, padx=5, pady=2)

        #Middle Frame
        MiddleFrame=Frame(Main_Frame,bd=10)
        MiddleFrame.place(x=10,y=150,width=980,height=340)
        #Image 5
        img_12 = Image.open("Images/Pic4.jpg")
        img_12 = img_12.resize((490, 340), Image.Resampling.LANCZOS)
        self.photoimg_12 = ImageTk.PhotoImage(img_12)
        lb1_img_12 = Label(MiddleFrame, image=self.photoimg_12)
        lb1_img_12.place(x=0, y=0, width=490, height=340)

        # Image 4
        img_13 = Image.open("Images/Pic5.jpg")
        img_13 = img_13.resize((490, 340), Image.Resampling.LANCZOS)
        self.photoimg_13 = ImageTk.PhotoImage(img_13)
        lb1_img_13 = Label(MiddleFrame, image=self.photoimg_13)
        lb1_img_13.place(x=490, y=0, width=500, height=340)


        #Search
        Search_Frame=Frame(Main_Frame,bd=2, bg="white")
        Search_Frame.place(x=1020,y=10,width=500,height=40)
        self.lb1Bill=Label(Search_Frame,font=("arial",12,"bold"),fg="white",bg="black",text="Bill Number")
        self.lb1Bill.grid(row=0,column=0,sticky=W,padx=1)

        self.txt_entry_Search=ttk.Entry(Search_Frame,textvariable=self.search_bill,font=("arial", 12,"bold"),width=24)
        self.txt_entry_Search.grid(row=0,column=1,sticky=W,padx=2)
        self.BtnSearch=Button(Search_Frame,text="Search",font=("arial",10,"bold"), bg="Black", fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnSearch.grid(row=0,column=2)



        #Rightframe Bill area
        RightLabelFrame=LabelFrame(Main_Frame,text="Bill Area",font=("times new roman",12,"bold"),bg="white",fg="#ff7f27")
        RightLabelFrame.place(x=1000,y=45,width=480,height=440)
        scroll_y=Scrollbar(RightLabelFrame,orient=VERTICAL)
        self.textarea=Text(RightLabelFrame,yscrollcommand=scroll_y.set, bg="white",fg="black",font=("times new roman",12,"bold"))
        scroll_y.pack(side=RIGHT,fill=Y)
        scroll_y.config(command=self.textarea.yview)
        self.textarea.pack(fill=BOTH,expand=1)

        #Bill counterLabelframe
        bottom_Frame = LabelFrame(Main_Frame, text="Bill Counter", font=("times new roman", 16, "bold"), bg="#740876",fg="#ff7f27")
        bottom_Frame.place(x=0, y=485, width=1520, height=125)

        self.lb1SubTotal = Label(bottom_Frame, text="Sub Total", font=("arial", 12, "bold"), bg="#740876", fg="black", bd=4)
        self.lb1SubTotal.grid(row=0, column=0, stick=W, padx=5, pady=2)

        self.EntrySubTotal = ttk.Entry(bottom_Frame, font=("arial", 10, "bold"), width=26)
        self.EntrySubTotal.grid(row=0, column=1, sticky=W, padx=5, pady=2)

        self.lb1_Tax = Label(bottom_Frame, text="Gov Tax", font=("arial", 12, "bold"), bg="#740876", fg="black", bd=4)
        self.lb1_Tax.grid(row=1, column=0, stick=W, padx=5, pady=2)

        self.EntryTax = ttk.Entry(bottom_Frame, font=("arial", 10, "bold"), width=26)
        self.EntryTax.grid(row=1, column=1, sticky=W, padx=5, pady=2)

        self.lb1AmountTotal = Label(bottom_Frame, text="Total", font=("arial", 12, "bold"), bg="#740876", fg="black", bd=4)
        self.lb1AmountTotal.grid(row=2, column=0, stick=W, padx=5, pady=2)

        self.EntryAmount = ttk.Entry(bottom_Frame, font=("arial", 10, "bold"), width=26)
        self.EntryAmount.grid(row=2, column=1, sticky=W, padx=5, pady=2)

        #Buttom frame
        Btn_Frame=Frame(bottom_Frame,bd=2,bg="white")
        Btn_Frame.place(x=320,y=0)
        self.BtnAddToCart=Button(Btn_Frame,command=self.AddItem,text="Add To Cart",font=("arial",15,"bold"),bg="Black",fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnAddToCart.grid(row=0,column=0)

        self.Btngenerate = Button(Btn_Frame,command=self.gen_bill ,text="Generate Bill", font=("arial", 15, "bold"), bg="Black",fg="white",activebackground="blue",width=15,cursor="hand2")
        self.Btngenerate.grid(row=0, column=1)

        self.BtnSave = Button(Btn_Frame, text="Save Bill", font=("arial", 15, "bold"), bg="Black", fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnSave.grid(row=0, column=2)

        self.BtnPrint = Button(Btn_Frame, text="Print", font=("arial", 15, "bold"), bg="Black", fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnPrint.grid(row=0, column=3)

        self.BtnClear = Button(Btn_Frame, text="Clear", font=("arial", 15, "bold"), bg="Black",fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnClear.grid(row=0, column=4)

        self.BtnExit = Button(Btn_Frame, text="Exit", font=("arial", 15, "bold"), bg="Black", fg="white",activebackground="blue",width=15,cursor="hand2")
        self.BtnExit.grid(row=0, column=5)
        self.welcome()
        self.l=[]
    #==================Function Declaration=============================
    def AddItem(self):
        # Constants
        TAX_RATE = 0.01  # Example tax rate (1%)

        # Get user inputs
        price = self.prices.get()  # Price of the product
        quantity = self.qty.get()  # Quantity of the product
        product_name = self.product.get()  # Name of the product

        # Validation
        if not product_name:
            messagebox.showerror("Error", "Please select the product name")
            return

        # Calculate item total and update cart
        item_total = price * quantity
        self.l.append(item_total)

        # Insert item details into the bill text area
        self.textarea.insert(END, f"\n {product_name}\t\t{quantity}\t\tRs.{item_total:.2f}")

        # Calculate totals
        subtotal = sum(self.l)
        tax = subtotal * TAX_RATE
        total = subtotal + tax

        # Update UI fields with calculated values
        self.sub_total.set(f'Rs.{subtotal:.2f}')
        self.tax_input.set(f'Rs.{tax:.2f}')
        self.total.set(f'Rs.{total:.2f}')

    def gen_bill(self):
        # Validation: Ensure items have been added to the cart
        if not self.l:  # Check if the cart is empty
            messagebox.showerror("Error", "Please add products to the cart")
            return

        # Generate the bill
        self.welcome()  # Call the welcome method to prepare the bill header

        # Insert summary details
        self.textarea.insert(END, "\n==================================================")
        self.textarea.insert(END, f"\n Sub Amount:\t\t\t{self.sub_total.get()}")
        self.textarea.insert(END, f"\n Tax Amount:\t\t\t{self.tax_input.get()}")
        self.textarea.insert(END, f"\n Total Amount:\t\t\t{self.total.get()}")
        self.textarea.insert(END, "\n==================================================")

    # def AddItem(self):
    #     Tax=1
    #     self.n=self.prices.get()
    #     self.m=self.qty.get()*self.n
    #     self.l.append(self.m)
    #     if self.product.get()=="":
    #         messagebox.showerror("Error","Please Select the Product Name")
    #     else:
    #         self.textarea.insert(END,f"\n {self.product.get()}\t\t{self.qty.get()}\t\t{self.m}")
    #         self.sub_total.set(str('Rs.%.2f'%(sum(self.l))))
    #         self.tax_input.set(str('Rs.%.2f' % ((((sum(self.l))-(self.prices.get()))*Tax)/100)))
    #         self.total.set(str('Rs.%.2f'%(((sum(self.l))+((((sum(self.l))-(self.prices.get()))*Tax)/100)))))
    #
    # def gen_bill(self):
    #     if self.product.get()=="":
    #         messagebox.showerror("Error","Please Add To Cart Product")
    #     else:
    #         text=self.textarea.get(10.0,(10.0+float(len(self.l))))
    #         self.welcome()
    #         self.textarea.insert(END,"\n==================================================")
    #         self.textarea.insert(END,"\n Sub Amount:\t\t\t{self.sub_total.get()}")
    #         self.textarea.insert(END, "\n Tax Amount:\t\t\t{self.tax_input.get()}")
    #         self.textarea.insert(END, "\n Total Amount:\t\t\t{self.total.get()}")
    #         self.textarea.insert(END, "\n=================================================")

    def welcome(self):
        self.textarea.delete(1.0,END)
        self.textarea.insert(END,"\t Welcome GTNWorld Mini Mall")
        self.textarea.insert(END,f"\n Bill Number:{self.bill_no.get()}")
        self.textarea.insert(END, f"\n Customer Name:{self.c_name.get()}")
        self.textarea.insert(END, f"\n Phone number:{self.c_phon.get()}")
        self.textarea.insert(END, f"\n Customer Email:{self.c_email.get()}")

        self.textarea.insert(END,"\n==================================================")
        self.textarea.insert(END,f"\n Products\t\t\tQTY\t\tPrice")
        self.textarea.insert(END, "\n==================================================")
        # self.textarea.insert(END,)
    def Categories(self,event=""):
        if self.Combo_Category.get()=="Clothing":
            self.ComboSubCategory.config(value=self.SubCatclothing)
            self.ComboSubCategory.current(0)

        if self.Combo_Category.get()=="LifeStyle":
            self.ComboSubCategory.config(value=self.SubCatlifestyle)
            self.ComboSubCategory.current(0)

        if self.Combo_Category.get()=="Mobiles":
            self.ComboSubCategory.config(value=self.SubCatMobiles)
            self.ComboSubCategory.current(0)
    def Product_add(self,event=""):
        if self.ComboSubCategory.get()=="Pant":
            self.ComboProduct.config(value=self.pant)
            self.ComboProduct.current(0)
            #T-shirt, Shirt
        if self.ComboSubCategory.get()=="T-Shirt":
            self.ComboProduct.config(value=self.T_Shirt)
            self.ComboProduct.current(0)
        if self.ComboSubCategory.get()=="Shirt":
            self.ComboProduct.config(value=self.Shirt)
            self.ComboProduct.current(0)
    #LifeStyles
        if self.ComboSubCategory.get()=="Bath Soap":
            self.ComboProduct.config(value=self.Bath_soap)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="Face Cream":
            self.ComboProduct.config(value=self.Face_cream)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="Hair Oil":
            self.ComboProduct.config(value=self.Hair_oil)
            self.ComboProduct.current(0)

            #Mobile
        if self.ComboSubCategory.get()=="Iphone":
            self.ComboProduct.config(value=self.Iphone)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="Samsung":
            self.ComboProduct.config(value=self.Samsung)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="Nokia":
            self.ComboProduct.config(value=self.Nokia)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="RealMe":
            self.ComboProduct.config(value=self.RealMe)
            self.ComboProduct.current(0)

        if self.ComboSubCategory.get()=="OnePlus":
            self.ComboProduct.config(value=self.OnePlus)
            self.ComboProduct.current(0)
    def price(self,event=""):
        #pant
        if self.ComboProduct.get()=="Levis":
            self.Comboprice.config(value=self.price_levis)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Mufti":
            self.Comboprice.config(value=self.price_Mufti)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Spykar":
            self.Comboprice.config(value=self.price_Skykar)
            self.Comboprice.current(0)
            self.qty.set(1)
        #T-shirt
        if self.ComboProduct.get()=="Polo":
            self.Comboprice.config(value=self.price_Polo)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Roadster":
            self.Comboprice.config(value=self.price_roadster)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Jack&Jones":
            self.Comboprice.config(value=self.price_Jackjones)
            self.Comboprice.current(0)
            self.qty.set(1)
        #Shirt
        if self.ComboProduct.get()=="Peter England":
            self.Comboprice.config(value=self.price_Peter)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Louis":
            self.Comboprice.config(value=self.price_Louis)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Park Avenue":
            self.Comboprice.config(value=self.price_park)
            self.Comboprice.current(0)
            self.qty.set(1)
        #Bathsoap
        if self.ComboProduct.get()=="LifeBuy":
            self.Comboprice.config(value=self.price_life)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Lux":
            self.Comboprice.config(value=self.price_lux)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Santoor":
            self.Comboprice.config(value=self.price_Santoor)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Pearl":
            self.Comboprice.config(value=self.price_Pearl)
            self.Comboprice.current(0)
            self.qty.set(1)

        #FaceCream
        if self.ComboProduct.get()=="Fair&Love":
            self.Comboprice.config(value=self.price_fair)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Ponds":
            self.Comboprice.config(value=self.price_ponds)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Olay":
            self.Comboprice.config(value=self.price_olay)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Garnier":
            self.Comboprice.config(value=self.price_garnier)
            self.Comboprice.current(0)
            self.qty.set(1)

        # HairOil
        if self.ComboProduct.get()=="Parachute":
            self.Comboprice.config(value=self.price_para)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Jashmin":
            self.Comboprice.config(value=self.price_ashmin)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Baja":
            self.Comboprice.config(value=self.price__bajaj)
            self.Comboprice.current(0)
            self.qty.set(1)
        # Iphone Mobiles
        if self.ComboProduct.get()=="Iphone_X":
            self.Comboprice.config(value=self.price_ix)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Iphone_11":
            self.Comboprice.config(value=self.price_i11)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Iphone_12":
            self.Comboprice.config(value=self.price_i12)
            self.Comboprice.current(0)
            self.qty.set(1)

        # Samsung Mobiles
        if self.ComboProduct.get()=="Samsung S21":
            self.Comboprice.config(value=self.price_S21)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Samsung S22":
            self.Comboprice.config(value=self.price_S22)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Samsung S23":
            self.Comboprice.config(value=self.price_S23)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Samsung S24":
            self.Comboprice.config(value=self.price_S24)
            self.Comboprice.current(0)
            self.qty.set(1)
        #Nokia Mobiles
        if self.ComboProduct.get()=="Nokia C10":
            self.Comboprice.config(value=self.price_C10)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Nokia G10":
            self.Comboprice.config(value=self.price_G10)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="Nokia G20":
            self.Comboprice.config(value=self.price_G20)
            self.Comboprice.current(0)
            self.qty.set(1)
        #RealMe Mobiles
        if self.ComboProduct.get()=="RealMe 12":
            self.Comboprice.config(value=self.price_rel12)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="RealMe 13":
            self.Comboprice.config(value=self.price_rel13)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="RealMe Pro":
            self.Comboprice.config(value=self.price_repro)
            self.Comboprice.current(0)
            self.qty.set(1)

        #One Plus Mobiles
        if self.ComboProduct.get()=="OnePlus1":
            self.Comboprice.config(value=self.price_one1)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="OnePlus2":
            self.Comboprice.config(value=self.price_one2)
            self.Comboprice.current(0)
            self.qty.set(1)
        if self.ComboProduct.get()=="OnePlus3":
            self.Comboprice.config(value=self.price_one3)
            self.Comboprice.current(0)
            self.qty.set(1)




if __name__=='__main__':
    root=Tk()
    obj=Bill_App(root)
    root.mainloop()
