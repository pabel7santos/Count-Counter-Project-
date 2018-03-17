# Count-Counter-Project-
Count Counter Project - Android Developer Growth with Google - Udacity


<?xml version="1.0" encoding="utf-8"?>

<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.student.courtcounter.MainActivity">
    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:src="@drawable/count"
        android:scaleType="centerCrop"  />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingTop="60dp"
    android:orientation="horizontal"  >

        <LinearLayout
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:orientation="vertical"


              <TextView
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:text="TEAM A"
                    android:padding="7dp"
                    android:textSize="20dp"
                    android:textColor="#fff"
                    android:textStyle="bold"
                    android:gravity="center_horizontal" />

             <TextView
                    android:id="@+id/team_a_score"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:text="0"
                    android:textSize="80dp"
                    android:padding="7dp"
                    android:textColor="#ffff00"
                    android:textStyle="bold"
                    android:gravity="center_horizontal" />

                        <Button
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:text="+3 Points"
                            android:layout_margin="7dp"
                            android:onClick="addThreeForTeamA" />

                        <Button
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:text="+2 Points"
                            android:layout_margin="7dp"
                            android:onClick="addTwoForTeamA" />

                        <Button
                            android:layout_width="match_parent"
                            android:layout_height="wrap_content"
                            android:text="Free Throw"
                            android:layout_margin="7dp"
                            android:onClick="addOneThrowTeamA" />
        </LinearLayout>

        <LinearLayout
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:orientation="vertical"
            tools:context="com.example.student.courtcounter.MainActivity">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="TEAM B"
                android:padding="7dp"
                android:textSize="20dp"
                android:textColor="#fff"
                android:textStyle="bold"
                android:gravity="center_horizontal" />

            <TextView
                android:id="@+id/team_b_score"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="0"
                android:padding="7dp"
                android:textSize="80dp"
                android:textColor="#ffff00"
                android:textStyle="bold"
                android:gravity="center_horizontal" />

                    <Button
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:text="+3 Points"
                        android:layout_margin="7dp"
                        android:onClick="addThreeForTeamB" />

                    <Button
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:text="+2 Points"
                        android:layout_margin="7dp"
                        android:onClick="addTwoForTeamB" />

                    <Button
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:text="Free Throw"
                        android:layout_margin="7dp"
                        android:onClick="addOneThrowTeamB" />
        </LinearLayout>

</RelativeLayout>

<Button
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Reset"
    android:layout_alignParentBottom="true"
    android:layout_centerHorizontal="true"
    android:onClick="resetScore"  />

</LinearLayout>



// FOR MainActivity.Java //
Check below Code:

package com.example.student.courtcounter;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;
import android.view.Menu;
import android.view.MenuItem;

public class MainActivity extends AppCompatActivity{
    // ADDING TWO VARIABLES FOR TEAM A AND TEAM B
    int scoreTeamA = 0;
    int scoreTeamB = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState)    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        displayForTeamA(0);
    }
    //              TEAM PLAYER A   //
    public void addThreeForTeamA(View view)    {    /*   displayForTeamA(3);  */
        scoreTeamA = scoreTeamA + 3;
        displayForTeamA(scoreTeamA); // THIS IS TO INCREASE THE SCORE FOR TEAM A BY 3 POINTS..
    }
    //
    public void addTwoForTeamA(View view)    {   /*  displayForTeamA(2);  */
        scoreTeamA = scoreTeamA + 2;
        displayForTeamA(scoreTeamA); // THIS IS TO INCREASE THE SCORE FOR TEAM A BY 3 POINTS..
    }
    //
    public void addOneThrowTeamA(View view)    {
        scoreTeamA = scoreTeamA + 1;
        displayForTeamA(scoreTeamA);
    }
    //
    public void displayForTeamA(int score)
    {
        TextView scoreView = (TextView) findViewById(R.id.team_a_score);
        scoreView.setText(String.valueOf(score));
    }
    //               TEAM PLAYER B    //
    public void addThreeForTeamB(View view)    {    /*   displayForTeamA(3);  */
        scoreTeamB = scoreTeamB + 3;
        displayForTeamB(scoreTeamB); // THIS IS TO INCREASE THE SCORE FOR TEAM A BY 3 POINTS..
    }
    //
    public void addTwoForTeamB(View view)    {   /*  displayForTeamA(2);  */
        scoreTeamB = scoreTeamB + 2;
        displayForTeamB(scoreTeamB); // THIS IS TO INCREASE THE SCORE FOR TEAM A BY 3 POINTS..
    }
    //
    public void addOneThrowTeamB(View view)    {
        scoreTeamB = scoreTeamB + 1;
        displayForTeamB(scoreTeamB);
    }
    //
    public void displayForTeamB(int score)
    {
        TextView scoreView = (TextView) findViewById(R.id.team_b_score);
        scoreView.setText(String.valueOf(score));
    }
    //  CREATING A RESET ACTION //
    public void resetScore(View view) {
        scoreTeamA = 0;
        scoreTeamB = 0;
        displayForTeamA(scoreTeamA);
        displayForTeamB(scoreTeamB);
    }
}
