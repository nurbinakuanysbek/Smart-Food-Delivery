#include <iostream>
#include <vector>
#include <string>
#include <map>
#include <iomanip>
#include <cstdlib>
#include <ctime>

using namespace std;

// Тағам құрылымы
struct Food {
    string name;
    int price;
};

// Себеттегі тауар құрылымы
struct CartItem {
    string name;
    int price;
    int quantity;
};

// Мейрамхана класы
class Restaurant {
public:
    string name;
    // Санаттар бойынша тағамдар тізімі (мысалы: "Пиццы", "Комбо")
    map<string, vector<Food>> menu;

    Restaurant(string n) : name(n) {}

    void addFood(string category, string foodName, int price) {
        menu[category].push_back({foodName, price});
    }
};

int main() {
    // Қазақ тілін консольде дұрыс көрсету үшін (жүйеге байланысты)
    setlocale(LC_ALL, "Kazakh");
    srand(time(0)); // Рандом уақыт үшін

    // --- ДЕРЕКТЕР ҚОРЫН ҚҰРУ ---
    vector<Restaurant> restaurants;

    // 1. Додо пицца
    Restaurant dodo("Додо пицца");
    dodo.addFood("Пиццы", "мясная", 2050);
    dodo.addFood("Пиццы", "мясная с цыпленком", 1550);
    dodo.addFood("Пиццы", "маргарита с Песто", 1300);
    dodo.addFood("Пиццы", "Сладкая пицца пирог", 1400);
    dodo.addFood("Пиццы", "Чоризо фреш", 1300);
    dodo.addFood("Пиццы", "сырная", 1300);
    dodo.addFood("Пиццы", "Терияки", 2690);
    dodo.addFood("Пиццы", "Додо микс", 2890);
    dodo.addFood("Пиццы", "четыре сезона", 2690);
    dodo.addFood("Пиццы", "Пеперони с грибами", 1550);
    dodo.addFood("Пиццы", "Пеперони", 1750);
    dodo.addFood("Пиццы", "Додо", 2350);

    dodo.addFood("Комбо", "соло комбо", 1600);
    dodo.addFood("Комбо", "Play Dodo комбо", 2800);
    dodo.addFood("Комбо", "2 пиццы", 4950);
    dodo.addFood("Комбо", "3 пиццы", 8190);
    dodo.addFood("Комбо", "пицца и 2 закуски", 5450);
    dodo.addFood("Комбо", "4 закуски", 4990);
    dodo.addFood("Комбо", "комбо завтрак на двоих", 4250);
    dodo.addFood("Комбо", "2 соуса", 690);

    dodo.addFood("Закуски", "паста мясная", 2790);
    dodo.addFood("Закуски", "ланчбокс охотничий", 2450);
    dodo.addFood("Закуски", "додстер", 1690);
    dodo.addFood("Закуски", "Цезарь ролл", 1490);
    dodo.addFood("Закуски", "сэндвич ветчина и сыр", 1890);
    dodo.addFood("Закуски", "куриные наггетсы", 990);
    dodo.addFood("Закуски", "картофель из печи", 790);
    dodo.addFood("Закуски", "салат цезарь", 2090);

    dodo.addFood("Коктейли", "Молочный Коктейль Солёная карамель", 1700);
    dodo.addFood("Коктейли", "Молочный коктейль с печеньем Орео", 1890);
    dodo.addFood("Коктейли", "Классический молочный коктейль", 1400);
    dodo.addFood("Коктейли", "шоколадный молочный коктейль", 1890);

    dodo.addFood("Кофе", "кофе капучино", 990);
    dodo.addFood("Кофе", "Кофе латте", 990);
    dodo.addFood("Кофе", "кофе американо", 890);

    dodo.addFood("Напитки", "Кока кола", 600);
    dodo.addFood("Напитки", "фанта", 600);
    dodo.addFood("Напитки", "спрайт", 600);
    dodo.addFood("Напитки", "fuse tea персик", 800);
    dodo.addFood("Напитки", "fusetea клубника-дыня", 800);
    dodo.addFood("Напитки", "fusetea mangо-ананас", 800);
    dodo.addFood("Напитки", "Сок Пикот Апельсин", 550);
    dodo.addFood("Напитки", "Сок Пико Яблоко", 550);
    dodo.addFood("Напитки", "Bonaqua газированная", 500);
    dodo.addFood("Напитки", "Bonaqua негазированная", 500);

    dodo.addFood("Соусы", "Сырный", 400);
    dodo.addFood("Соусы", "чесночный", 400);
    dodo.addFood("Соусы", "барбекю", 400);
    dodo.addFood("Соусы", "соус цезарь", 400);
    dodo.addFood("Соусы", "малиновое варенье", 400);
    restaurants.push_back(dodo);

    // 2. Бургер Кинг
    Restaurant bk("Бургер Кинг");
    bk.addFood("Самое популярное", "криспи чикен 1+1", 2100);
    bk.addFood("Самое популярное", "криспи чикен комбо", 3400);
    bk.addFood("Самое популярное", "Воппер Комбо", 4100);

    bk.addFood("Роял Боксы", "Роял Фэмили Бокс", 13500);
    bk.addFood("Роял Боксы", "Кинг Бокс", 13000);
    bk.addFood("Роял Боксы", "Роял Дуо", 7000);

    bk.addFood("Бургеры", "Двойной воппер", 3700);
    bk.addFood("Бургеры", "Двойной криспи чикен", 3100);
    bk.addFood("Бургеры", "острый воппер", 2900);
    bk.addFood("Бургеры", "Стейкхаус", 2800);
    bk.addFood("Бургеры", "Биг Кинг XL", 2700);

    bk.addFood("Напитки", "Red Bull Sugarfree(250ml)", 1400);
    bk.addFood("Напитки", "Red Bull Energy(250ml)", 1400);
    bk.addFood("Напитки", "Fusetea 0,5", 780);
    bk.addFood("Напитки", "Спрайт 0,5", 780);
    bk.addFood("Напитки", "Кока Кола 0,5", 780);
    bk.addFood("Напитки", "Фанта 0,5", 780);
    bk.addFood("Напитки", "Сок Пико 200мл", 500);
    bk.addFood("Напитки", "Вода Bonaqua 0,5", 450);
    restaurants.push_back(bk);

    // 3. Салам Бро
    Restaurant sb("Салам Бро");
    sb.addFood("Комбо", "Комбо для двоих", 5820);
    sb.addFood("Комбо", "Нано Комбо", 3340);
    sb.addFood("Комбо", "Комбо для одного(говяжий)", 3120);
    sb.addFood("Комбо", "комбо для одного(куриный)", 3000);

    sb.addFood("Бургеры", "Чизбургер микс", 2400);
    sb.addFood("Бургеры", "Чизбургер двойной", 2340);
    sb.addFood("Бургеры", "Гамбургер", 2280);
    sb.addFood("Бургеры", "Гамбургер двойной(говяжий)", 2100);
    sb.addFood("Бургеры", "Гамбургер двойной(куриный)", 1920);

    sb.addFood("Закуски", "Наггетсы(20шт)", 3530);
    sb.addFood("Закуски", "Наггетсы(9шт)", 2030);
    sb.addFood("Закуски", "Сырные шарики", 1430);
    sb.addFood("Закуски", "Наггетсы(6 шт)", 1370);
    sb.addFood("Закуски", "Картошка фри", 830);

    sb.addFood("Соусы и добавки", "Сыр", 300);
    sb.addFood("Соусы и добавки", "Кетчуп", 240);
    sb.addFood("Соусы и добавки", "Соус Барбекю", 240);
    sb.addFood("Соусы и добавки", "Сырный соус", 240);
    sb.addFood("Соусы и добавки", "Халапеньо", 180);

    sb.addFood("Напитки", "Пико 0,5", 900);
    sb.addFood("Напитки", "Кока Кола 0,5", 780);
    sb.addFood("Напитки", "Фанта 0,5", 780);
    sb.addFood("Напитки", "Спрайт 0,5", 780);
    sb.addFood("Напитки", "Fusetea 0,5", 780);
    sb.addFood("Напитки", "Bonaqua", 520);
    restaurants.push_back(sb);

    // --- ИНТЕРФЕЙС ПАЙДАЛАНУШЫ ---
    cout << "=========================================\n";
    cout << "   Smart Food Delivery-ге қош келдіңіз!  \n";
    cout << "=========================================\n\n";

    // 1. Мейрамхана таңдау
    cout << "Мейрамхананы таңдаңыз:\n";
    for (size_t i = 0; i < restaurants.size(); ++i) {
        cout << "[" << i + 1 << "] " << restaurants[i].name << "\n";
    }
    
    int resChoice;
    cout << "\nНөмірді енгізіңіз: ";
    cin >> resChoice;
    if (resChoice < 1 || resChoice > (int)restaurants.size()) {
        cout << "Қате таңдау! Бағдарлама аяқталды.\n";
        return 0;
    }

    Restaurant& selectedRes = restaurants[resChoice - 1];
    vector<CartItem> cart;

    // 2. Тағамдарды таңдау циклі
    while (true) {
        cout << "\n====== " << selectedRes.name << " МӘЗІРІ ======\n";
        
        // Барлық тағамдарды бір тізімге индекстеп жинау
        vector<Food> currentMenuFlat;
        int index = 1;

        for (auto const& [category, foods] : selectedRes.menu) {
            cout << "\n--- " << category << " ---\n";
            for (auto const& food : foods) {
                cout << "[" << index << "] " << food.name << " - " << food.price << " тг\n";
                currentMenuFlat.push_back(food);
                index++;
            }
        }

        cout << "\n[0] Тапсырысты аяқтау (Себетке өту)\n";
        int foodChoice;
        cout << "\nТағам нөмірін таңдаңыз: ";
        cin >> foodChoice;

        if (foodChoice == 0) break;

        if (foodChoice < 1 || foodChoice >= index) {
            cout << "Мұндай тағам жоқ, қайтадан байқап көріңіз.\n";
            continue;
        }

        int quantity;
        cout << "Санын енгізіңіз: ";
        cin >> quantity;
        if (quantity <= 0) quantity = 1;

        Food chosenFood = currentMenuFlat[foodChoice - 1];
        
        // Себетте бұрын бар-жоғын тексеру
        bool found = false;
        for (auto& item : cart) {
            if (item.name == chosenFood.name) {
                item.quantity += quantity;
                found = true;
                break;
            }
        }
        if (!found) {
            cart.push_back({chosenFood.name, chosenFood.price, quantity});
        }
        cout << "✔ " << chosenFood.name << " себетке қосылды.\n";
    }

    // 3. Тапсырысты рәсімдеу
    if (cart.empty()) {
        cout << "\nСебет бос. Тапсырыс бас тартылды.\n";
        return 0;
    }

    string address;
    cout << "\nЖеткізу мекенжайын енгізіңіз (мысалы: Абай көшесі, 45): ";
    cin.ignore(); // Буферді тазалау
    getline(cin, address);

    // 4. Есептеу логикасы
    int totalFoodSum = 0;
    cout << "\n=========================================\n";
    cout << "               СІЗДІҢ ЧЕКІҢІЗ            \n";
    cout << "=========================================\n";
    cout << "Мейрамхана: " << selectedRes.name << "\n\n";

    for (auto const& item : cart) {
        int itemCost = item.price * item.quantity;
        totalFoodSum += itemCost;
        cout << " - " << item.name << " x" << item.quantity << " = " << itemCost << " тг\n";
    }

    // Логика: Егер тапсырыс 5000 теңгеден асса, жеткізу тегін, әйтпесе 700 теңге
    int deliveryFee = (totalFoodSum >= 5000) ? 0 : 700;
    int finalTotal = totalFoodSum + deliveryFee;
    int deliveryTime = rand() % 26 + 25; // 25 пен 50 минут аралығындағы кездейсоқ сан

    cout << "-----------------------------------------\n";
    cout << "Тағамдар құны: " << totalFoodSum << " тг\n";
    cout << "Жеткізу ақысы: " << deliveryFee << " тг " << (deliveryFee == 0 ? "(ТЕГІН - 5000 тг асқан соң)" : "") << "\n";
    cout << "ЖАЛПЫ ТӨЛЕМ  : " << finalTotal << " тг\n";
    cout << "-----------------------------------------\n";
    cout << "Мекенжай     : " << address << "\n";
    cout << "Курьердің жету уақыты: ~" << deliveryTime << " минут\n";
    cout << "=========================================\n";
    cout << "Асыңыз дәмді болсын! Ас үй жүйесі тапсырысты қабылдады.\n";

    return 0;
}
