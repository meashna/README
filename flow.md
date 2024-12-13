// Below is a comprehensive example integrating the final result screen and related screens into your existing project structure.
// This code is illustrative and may require adjustments (imports, styles, localization, etc.) based on your project specifics.
// The focus is on file structure, route integration, and the UI flow.
// Assume that APIs, repositories, and cubits related to fetching or saving data have already been set up similarly to your existing pattern.

// FILE: lib/src/screens/app_screens.dart
// Add these new route names:
class AppScreens {
  static const periodCalendarGoal = "/periodCalendarGoal";
  static const addLogScreen = "/addLogScreen";
  static const flowSelectionScreen = "/flowSelectionScreen";
  static const cycleTimelineScreen = "/cycleTimelineScreen";
  static const cyclePatternScreen = "/cyclePatternScreen";
  static const currentCycleQuestion1Screen = "/currentCycleQuestion1Screen";
  static const currentCycleQuestion2Screen = "/currentCycleQuestion2Screen";
  static const fertilityPredictionScreen = "/fertilityPredictionScreen";
  // ... existing route constants
}

// FILE: lib/src/utils/routes/app_router.dart
// Add the routes to onGenerateRoute switch case:
import 'package:flutter/material.dart';
import 'package:firebase_messaging/firebase_messaging.dart';
import 'package:curate/src/screens/app_screens.dart';
import 'package:curate/src/data/models/response/healthLog/HealthLogData.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/period_calendar_goal_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/add_log_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/flow_selection_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/cycle_timeline_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/cycle_pattern_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/current_cycle_question1_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/current_cycle_question2_screen.dart';
import 'package:curate/src/screens/mainscreen/profile/periodLog/new_flow/fertility_prediction_screen.dart';
// import other screens as per existing code...

Route<dynamic> generateRoute(RouteSettings settings) {
  switch (settings.name) {
    case AppScreens.periodCalendarGoal:
      return _buildRoute(settings, const PeriodCalendarGoalScreen());

    case AppScreens.addLogScreen:
      return _buildRoute(settings, const AddLogScreen());

    case AppScreens.flowSelectionScreen:
      return _buildRoute(settings, const FlowSelectionScreen());

    case AppScreens.cycleTimelineScreen:
      return _buildRoute(settings, const CycleTimelineScreen());

    case AppScreens.cyclePatternScreen:
      return _buildRoute(settings, const CyclePatternScreen());

    case AppScreens.currentCycleQuestion1Screen:
      return _buildRoute(settings, const CurrentCycleQuestion1Screen());

    case AppScreens.currentCycleQuestion2Screen:
      return _buildRoute(settings, const CurrentCycleQuestion2Screen());

    case AppScreens.fertilityPredictionScreen:
      return _buildRoute(settings, const FertilityPredictionScreen());

    // ... existing route cases

    default:
      // Return a default route or 404 screen
      return MaterialPageRoute(builder: (_) => const SizedBox());
  }
}

Route<dynamic> _buildRoute(RouteSettings settings, Widget builder) {
  return MaterialPageRoute(builder: (_) => builder, settings: settings);
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/period_calendar_goal_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/screens/app_screens.dart';
import 'package:curate/src/widgets/app_button.dart';

class PeriodCalendarGoalScreen extends StatelessWidget {
  const PeriodCalendarGoalScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Period Calendar")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("What is your goal with period tracking", style: TextStyle(fontSize: 18)),
            const SizedBox(height: 20),
            RadioListTile(
              title: const Text("Trying to conceive"),
              value: 1, groupValue: 1, onChanged: (v) {},
            ),
            RadioListTile(
              title: const Text("Track my cycle"),
              value: 2, groupValue: 1, onChanged: (v) {},
            ),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.addLogScreen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/add_log_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/screens/app_screens.dart';
import 'package:curate/src/widgets/app_button.dart';

class AddLogScreen extends StatelessWidget {
  const AddLogScreen({Key? key}) : super(key: key);

  // Mock calendar for last three periods
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Add log")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("New period calendar", style: TextStyle(fontSize: 18)),
            const SizedBox(height: 16),
            const Text("Mark the date range of your last three periods"),
            const SizedBox(height: 16),
            const Text("February 2024", style: TextStyle(fontSize: 16)),
            const SizedBox(height: 8),
            Expanded(
              child: GridView.builder(
                itemCount: 28,
                gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
                    crossAxisCount: 7, childAspectRatio: 1.2),
                itemBuilder: (context, index) {
                  return Center(child: Text("${index + 1}"));
                },
              ),
            ),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.flowSelectionScreen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/flow_selection_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/screens/app_screens.dart';
import 'package:curate/src/widgets/app_button.dart';

class FlowSelectionScreen extends StatelessWidget {
  const FlowSelectionScreen({Key? key}) : super(key: key);

  // How is your flow?
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Periods")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("How is your flow?", style: TextStyle(fontSize: 18)),
            const SizedBox(height: 16),
            RadioListTile(title: const Text("Very less"), value: 1, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Normal"), value: 2, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Heavy bleeding"), value: 3, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Pass clots with my bleeding"), value: 4, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Heavy bleeding with clots"), value: 5, groupValue: 1, onChanged: (v) {}),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.cycleTimelineScreen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/cycle_timeline_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/widgets/app_button.dart';
import 'package:curate/src/screens/app_screens.dart';

class CycleTimelineScreen extends StatelessWidget {
  const CycleTimelineScreen({Key? key}) : super(key: key);

  // Timeline screen
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Periods")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("Days since last cycle", style: TextStyle(fontSize: 18)),
            const SizedBox(height: 8),
            const Text("4", style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold)),
            const SizedBox(height: 8),
            const Text("Normal period cycles range from 21-35 days."),
            const SizedBox(height: 16),
            const Text("Timeline", style: TextStyle(fontSize: 18)),
            const SizedBox(height: 12),
            ListTile(
              title: const Text("13-18 Nov 2022"),
              subtitle: const Text("Duration: 4 Days\nFlow: Medium"),
            ),
            ListTile(
              title: const Text("13-18 Oct 2022"),
              subtitle: const Text("Duration: 4 Days\nFlow: Medium"),
            ),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.cyclePatternScreen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/cycle_pattern_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/screens/app_screens.dart';
import 'package:curate/src/widgets/app_button.dart';

class CyclePatternScreen extends StatelessWidget {
  const CyclePatternScreen({Key? key}) : super(key: key);

  // Cycle pattern inputs
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Cycle pattern")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("What is the used time between your two periods?", style: TextStyle(fontSize: 16)),
            const SizedBox(height: 8),
            DropdownButton<int>(
              items: List.generate(15, (index) => DropdownMenuItem(value: index + 21, child: Text("${index+21} days"))),
              onChanged: (val) {},
            ),
            TextButton(onPressed: () {}, child: const Text("My cycle varies alot")),
            const SizedBox(height: 16),
            const Text("How many days does your bleeding usually last?", style: TextStyle(fontSize: 16)),
            const SizedBox(height: 8),
            DropdownButton<int>(
              items: List.generate(10, (index) => DropdownMenuItem(value: index + 1, child: Text("${index+1} days"))),
              onChanged: (val) {},
            ),
            TextButton(onPressed: () {}, child: const Text("My cycle varies alot")),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.currentCycleQuestion1Screen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/current_cycle_question1_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/widgets/app_button.dart';
import 'package:curate/src/screens/app_screens.dart';

class CurrentCycleQuestion1Screen extends StatelessWidget {
  const CurrentCycleQuestion1Screen({Key? key}) : super(key: key);

  // Birth control question
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Your current cycle")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("Have you used birth control in the last 6 months?", style: TextStyle(fontSize: 16)),
            RadioListTile(title: const Text("No"), value: 1, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Still using"), value: 2, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Was using, now stopped"), value: 3, groupValue: 1, onChanged: (v) {}),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.currentCycleQuestion2Screen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/current_cycle_question2_screen.dart
import 'package:flutter/material.dart';
import 'package:curate/src/widgets/app_button.dart';
import 'package:curate/src/screens/app_screens.dart';

class CurrentCycleQuestion2Screen extends StatelessWidget {
  const CurrentCycleQuestion2Screen({Key? key}) : super(key: key);

  // Fertility treatments question
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Your current cycle")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("Are you under any fertility treatments?", style: TextStyle(fontSize: 16)),
            RadioListTile(title: const Text("No"), value: 1, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("IVI"), value: 2, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("IVF"), value: 3, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Ovulation Induction Medicines"), value: 4, groupValue: 1, onChanged: (v) {}),
            RadioListTile(title: const Text("Others"), value: 5, groupValue: 1, onChanged: (v) {}),
            const Spacer(),
            AppButton(
              text: "Continue",
              onClicked: () {
                Navigator.pushNamed(context, AppScreens.fertilityPredictionScreen);
              },
            )
          ],
        ),
      ),
    );
  }
}

// FILE: lib/src/screens/mainscreen/profile/periodLog/new_flow/fertility_prediction_screen.dart
import 'package:flutter/material.dart';

class FertilityPredictionScreen extends StatelessWidget {
  const FertilityPredictionScreen({Key? key}) : super(key: key);

  // Final result screen
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Your current cycle")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            const Text("Today, Feb 22", textAlign: TextAlign.center),
            const Text("Day 16", textAlign: TextAlign.center),
            const Text("Peak fertility", textAlign: TextAlign.center),
            const Text("chances of conceiving", textAlign: TextAlign.center),
            const Text("High", textAlign: TextAlign.center, style: TextStyle(fontWeight: FontWeight.bold)),
            const SizedBox(height: 16),
            const Text("Your cycle predictions", style: TextStyle(fontSize: 18), textAlign: TextAlign.center),
            const SizedBox(height: 8),
            const Text("Your next periods may start on\nNov 5", textAlign: TextAlign.center),
            const Text("You are likely to ovulate\nOct 18", textAlign: TextAlign.center),
            const Text("Best chances of conceiving are from\nOct 18", textAlign: TextAlign.center),
            const Spacer(),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceAround,
              children: [
                TextButton(onPressed: () {}, child: const Text("Home")),
                TextButton(onPressed: () {}, child: const Text("My plan")),
                TextButton(onPressed: () {}, child: const Text("Chat")),
                TextButton(onPressed: () {}, child: const Text("Profile")),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// NOTE: Repository code (user_repository.dart, user_repository_impl.dart) can be reused from your previous setup.
// If no new API calls are required, you don't need to add or modify them. The screens above can call the same methods 
// (addPatientLog, getPeriodFlows, updatePatientLog, etc.) as shown in your original code.
//
// For example, if the initial steps (selecting dates, selecting flow, etc.) require saving data to the server,
// you can call methods in the AddFlowCubit or other cubits you’ve already created from these screens. 
// The final screen (FertilityPredictionScreen) might just display processed data retrieved through a repository call 
// or stored state in a cubit.
//
// Ensure that the logic and state management (BLoC/Cubit) that you used previously is integrated here as well.
// For brevity, it's not fully shown again, but you would follow the same pattern as in your existing codebase.
