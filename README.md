Custom lightweight open source GUI for c++. Requires openGL to render

GUI objects can be created like:

	shared_ptr<gui> my_gui = make_shared<gui>();

	shared_ptr<gui_obj> ip_input = make_shared<gui_input>("ip_input", "IP", "127.0.0.1", 0, 0, 200, 50);
	shared_ptr<gui_obj> port_input = make_shared<gui_input>("port_input", "Port", DEFAULT_PORT, 0, 50, 200, 50);
	

	shared_ptr<gui_button> client_connect_button = make_shared<gui_button>("client_connect_button", "Connect to server", 0, 100, 200, 50);
	client_connect_button->set_callback_function(start_client);

	shared_ptr<gui_text_view> chat_text_view = make_shared<gui_text_view>("chat_text_view", 200, 0, 800, 500);
	chat_text_view->set_app(my_app);

	shared_ptr<gui_obj> chat_input = make_shared<gui_input>("chat_input", "Type message here...", "", 210, 455, 450, 40);


	my_gui->add_object(ip_input);
	my_gui->add_object(port_input);
	my_gui->add_object(dynamic_pointer_cast<gui_obj>(client_connect_button));
	my_gui->add_object(dynamic_pointer_cast<gui_obj>(chat_text_view));
	my_gui->add_object(chat_input);

In your draw() method, add
	my_gui->draw();
	

Get value from an input
string ip = my_app->my_gui->get_value("ip_input");

Get the active input
my_gui->get_active_input();

Mouse hover over an input
my_gui->hover(x, y);


Example Usage of this GUI
![Example](https://i.imgur.com/h4aUQ3u.png)
