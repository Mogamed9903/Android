using System;
using System.Data;
using System.Data.SqlClient;
using System.Windows.Forms;

public partial class MainForm : Form
{
    private TextBox txtCustomerName, txtAddress, txtPhone;
    private ComboBox cmbTaxiType, cmbCapacity, cmbServiceClass;
    private Button btnRegisterOrder;
    private DataGridView dgvOrders;

    public MainForm()
    {
        InitializeComponent();
        InitializeUI();
    }

    private void InitializeUI()
    {
        // Инициализация элементов управления и их размещение
        txtCustomerName = new TextBox();
        txtAddress = new TextBox();
        txtPhone = new TextBox();
        cmbTaxiType = new ComboBox();
        cmbCapacity = new ComboBox();
        cmbServiceClass = new ComboBox();
        btnRegisterOrder = new Button();
        dgvOrders = new DataGridView();

        // Настройка свойств элементов
        // ...

        // Добавление элементов на форму
        Controls.Add(txtCustomerName);
        Controls.Add(txtAddress);
        Controls.Add(txtPhone);
        Controls.Add(cmbTaxiType);
        Controls.Add(cmbCapacity);
        Controls.Add(cmbServiceClass);
        Controls.Add(btnRegisterOrder);
        Controls.Add(dgvOrders);

        // Размещение элементов на форме
        // ...

        // Добавление обработчика события для кнопки регистрации заказа
        btnRegisterOrder.Click += btnRegisterOrder_Click;

        // Загрузка данных в ComboBox'ы
        LoadTaxiTypes();
        LoadCapacities();
        LoadServiceClasses();
    }

    private void btnRegisterOrder_Click(object sender, EventArgs e)
    {
        // Получение данных из элементов управления
        string customerName = txtCustomerName.Text;
        string address = txtAddress.Text;
        string phone = txtPhone.Text;
        string taxiType = cmbTaxiType.Text;
        string capacity = cmbCapacity.Text;
        string serviceClass = cmbServiceClass.Text;

        // Вставка данных в базу данных
        DatabaseManager.InsertOrder(customerName, address, phone, taxiType, capacity, serviceClass);

        // Обновление DataGridView
        RefreshOrdersDataGridView();
    }

    private void RefreshOrdersDataGridView()
    {
        dgvOrders.DataSource = DatabaseManager.GetOrders();
    }

    private void LoadTaxiTypes()
    {
        // Загрузка видов такси в ComboBox
        // ...
    }

    private void LoadCapacities()
    {
        // Загрузка грузоподъемностей в ComboBox
        // ...
    }

    private void LoadServiceClasses()
    {
        // Загрузка классов обслуживания в ComboBox
        // ...
    }
}
