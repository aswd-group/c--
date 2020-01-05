#include<bits/stdc++.h>
#include<string>
#include<windows.h>
using namespace std;

struct varable
{
	string type;
	string value;
};

string program[1000];
string examples[10] =
{
	"include<iostream>\nint main() {\n	   int a, b;\n	cin >> a >> b;\n	cout << a + b << endl;\n	return 0;\n}"
};

vector <varable> varables;

void find_var_type(string type_s)
{
	
}


void lang_parse(string s, string op_type, int line)
{
	if (op_type == "import:")
	{
		string s1(s, 1);
		program[line] = "#include <" + s1 + ">";
	}
	if (op_type == "func")
	{
		if (s != " main()")
		{
			program[line] = "auto" + s  + "{";
		}
		else
		{
			program[line] = "int" + s + "{";
		}
	}
	if (op_type == "endfunc")
	{
		program[line] = "}";
	}
	if (op_type == "define:")
	{
		program[line] = s + ";";
	}
	if (op_type == "assign:")
	{
		program[line] = s + ";";
	}
	if (op_type == "input:")
	{
		program[line] = "std::cin >> " + s + ";";
	}
	if (op_type == "print:")
	{
		program[line] = "std::cout << " + s + ";";
	}
	if (op_type == "return:")
	{
		program[line] = "return " + s + ";";
	}
	if (op_type == "if")
	{
		program[line] = "if (" + s + ") {";
	}
	if (op_type == "endif")
	{
		program[line] = "}";
	}
		//cout << program[line] << endl;
	if (op_type == "examples")
	{
		if (s == " a + b problem")
		{
			cout << "a + b problem:" << endl;
			cout << examples[0];
			exit(1);
		}
	}
	return ;
}

int main()
{
	int line = 0;
	while (1)
	{
		string op_type;
		string s;
		cin >> op_type;
		if (op_type == "parse")
		{
			freopen("test.cpp", "w", stdout);
			for (int i = 0; i < line; i++)
			{
				cout << program[i] << endl;
			}
			fclose(stdout);
			cout << "parsed!" << endl;
		}
		if (op_type == "run")
		{
			//run
		}
		getline(cin, s);
		lang_parse(s, op_type, line++);
		
	}
	return 0;
}
