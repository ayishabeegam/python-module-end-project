 {
 "cells": [
  {
   "cell_type": "markdown",
   "id": "9e2e0e82",
   "metadata": {},
   "source": [
    "## Module End Project"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "8090724f",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "b64c9e84",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Name</th>\n",
       "      <th>Team</th>\n",
       "      <th>Number</th>\n",
       "      <th>Position</th>\n",
       "      <th>Age</th>\n",
       "      <th>Height</th>\n",
       "      <th>Weight</th>\n",
       "      <th>College</th>\n",
       "      <th>Salary</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Avery Bradley</td>\n",
       "      <td>Boston Celtics</td>\n",
       "      <td>0</td>\n",
       "      <td>PG</td>\n",
       "      <td>25</td>\n",
       "      <td>06-Feb</td>\n",
       "      <td>180</td>\n",
       "      <td>Texas</td>\n",
       "      <td>7730337.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Jae Crowder</td>\n",
       "      <td>Boston Celtics</td>\n",
       "      <td>99</td>\n",
       "      <td>SF</td>\n",
       "      <td>25</td>\n",
       "      <td>06-Jun</td>\n",
       "      <td>235</td>\n",
       "      <td>Marquette</td>\n",
       "      <td>6796117.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>John Holland</td>\n",
       "      <td>Boston Celtics</td>\n",
       "      <td>30</td>\n",
       "      <td>SG</td>\n",
       "      <td>27</td>\n",
       "      <td>06-May</td>\n",
       "      <td>205</td>\n",
       "      <td>Boston University</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>R.J. Hunter</td>\n",
       "      <td>Boston Celtics</td>\n",
       "      <td>28</td>\n",
       "      <td>SG</td>\n",
       "      <td>22</td>\n",
       "      <td>06-May</td>\n",
       "      <td>185</td>\n",
       "      <td>Georgia State</td>\n",
       "      <td>1148640.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Jonas Jerebko</td>\n",
       "      <td>Boston Celtics</td>\n",
       "      <td>8</td>\n",
       "      <td>PF</td>\n",
       "      <td>29</td>\n",
       "      <td>06-Oct</td>\n",
       "      <td>231</td>\n",
       "      <td>NaN</td>\n",
       "      <td>5000000.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "            Name            Team  Number Position  Age  Height  Weight  \\\n",
       "0  Avery Bradley  Boston Celtics       0       PG   25  06-Feb     180   \n",
       "1    Jae Crowder  Boston Celtics      99       SF   25  06-Jun     235   \n",
       "2   John Holland  Boston Celtics      30       SG   27  06-May     205   \n",
       "3    R.J. Hunter  Boston Celtics      28       SG   22  06-May     185   \n",
       "4  Jonas Jerebko  Boston Celtics       8       PF   29  06-Oct     231   \n",
       "\n",
       "             College     Salary  \n",
       "0              Texas  7730337.0  \n",
       "1          Marquette  6796117.0  \n",
       "2  Boston University        NaN  \n",
       "3      Georgia State  1148640.0  \n",
       "4                NaN  5000000.0  "
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df = pd.read_csv('myexcel.csv')\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "4a2a0e4f",
   "metadata": {},
   "outputs": [],
   "source": [
    "df['Height']=np.random.randint(150,181,size=len(df))\n",
    "df.fillna('',inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "id": "07a8a440",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "            Name            Team  Number Position  Age  Height  Weight  \\\n",
      "0  Avery Bradley  Boston Celtics       0       PG   25     152     180   \n",
      "1    Jae Crowder  Boston Celtics      99       SF   25     172     235   \n",
      "2   John Holland  Boston Celtics      30       SG   27     166     205   \n",
      "3    R.J. Hunter  Boston Celtics      28       SG   22     163     185   \n",
      "4  Jonas Jerebko  Boston Celtics       8       PF   29     176     231   \n",
      "\n",
      "             College     Salary  \n",
      "0              Texas  7730337.0  \n",
      "1          Marquette  6796117.0  \n",
      "2  Boston University             \n",
      "3      Georgia State  1148640.0  \n",
      "4                     5000000.0  \n"
     ]
    }
   ],
   "source": [
    "print(df.head())"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "e884d2ee",
   "metadata": {},
   "source": [
    "##### 1.How many are there in each Team and the percentage splitting with respect to the total employees."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "7a032a09",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "                      Team  Count  Percentage\n",
      "0     New Orleans Pelicans     19    4.148472\n",
      "1        Memphis Grizzlies     18    3.930131\n",
      "2                Utah Jazz     16    3.493450\n",
      "3          New York Knicks     16    3.493450\n",
      "4          Milwaukee Bucks     16    3.493450\n",
      "5            Brooklyn Nets     15    3.275109\n",
      "6   Portland Trail Blazers     15    3.275109\n",
      "7    Oklahoma City Thunder     15    3.275109\n",
      "8           Denver Nuggets     15    3.275109\n",
      "9       Washington Wizards     15    3.275109\n",
      "10              Miami Heat     15    3.275109\n",
      "11       Charlotte Hornets     15    3.275109\n",
      "12           Atlanta Hawks     15    3.275109\n",
      "13       San Antonio Spurs     15    3.275109\n",
      "14         Houston Rockets     15    3.275109\n",
      "15          Boston Celtics     15    3.275109\n",
      "16          Indiana Pacers     15    3.275109\n",
      "17         Detroit Pistons     15    3.275109\n",
      "18     Cleveland Cavaliers     15    3.275109\n",
      "19           Chicago Bulls     15    3.275109\n",
      "20        Sacramento Kings     15    3.275109\n",
      "21            Phoenix Suns     15    3.275109\n",
      "22      Los Angeles Lakers     15    3.275109\n",
      "23    Los Angeles Clippers     15    3.275109\n",
      "24   Golden State Warriors     15    3.275109\n",
      "25         Toronto Raptors     15    3.275109\n",
      "26      Philadelphia 76ers     15    3.275109\n",
      "27        Dallas Mavericks     15    3.275109\n",
      "28           Orlando Magic     14    3.056769\n",
      "29  Minnesota Timberwolves     14    3.056769\n"
     ]
    }
   ],
   "source": [
    "team_counts=df['Team'].value_counts()\n",
    "percentage_split=(team_counts/len(df))*100\n",
    "team_stats=pd.DataFrame({'Team':team_counts.index,'Count': team_counts.values,'Percentage':percentage_split.values})\n",
    "print(team_stats)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "612424bf",
   "metadata": {},
   "source": [
    "##### 2.Segregate the employees w.r.t different positions."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "354e932c",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Position\n",
      "SG    102\n",
      "PF    100\n",
      "PG     92\n",
      "SF     85\n",
      "C      79\n",
      "Name: count, dtype: int64\n"
     ]
    }
   ],
   "source": [
    "position_counts=df['Position'].value_counts()\n",
    "print(position_counts)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "1b2be381",
   "metadata": {},
   "source": [
    "##### 3.Find from which age group most of the employees belong to."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "892581ce",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Age\n",
       "24    47\n",
       "25    46\n",
       "27    41\n",
       "23    41\n",
       "26    36\n",
       "28    31\n",
       "30    31\n",
       "29    28\n",
       "22    26\n",
       "31    22\n",
       "20    19\n",
       "21    19\n",
       "33    14\n",
       "32    13\n",
       "34    10\n",
       "36    10\n",
       "35     9\n",
       "37     4\n",
       "38     4\n",
       "40     3\n",
       "39     2\n",
       "19     2\n",
       "Name: count, dtype: int64"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df['Age'].value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "id": "52246d22",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Age\n",
       "24    47\n",
       "Name: count, dtype: int64"
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.Age.value_counts().sort_values(ascending = False).head(1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "b32a8662",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Age Group\n",
      "21-30    334\n",
      "31-40    119\n",
      "41-50      3\n",
      "0-20       2\n",
      "51-60      0\n",
      "60+        0\n",
      "Name: count, dtype: int64\n"
     ]
    }
   ],
   "source": [
    "age_bins=[0,20,30,40,50,60,np.inf]\n",
    "age_labels=['0-20','21-30','31-40','41-50','51-60','60+']\n",
    "df['Age Group']=pd.cut(df['Age'],bins=age_bins,labels=age_labels,right=False)\n",
    "age_group_counts=df['Age Group'].value_counts()\n",
    "print(age_group_counts)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "dd9f6c4e",
   "metadata": {},
   "source": [
    "##### 4.Find out under which team and position, spending in terms of salary is high."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "id": "803a1596",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Team with highest spending : Los Angeles Lakers\n",
      "Postion with highest spending : SF\n"
     ]
    }
   ],
   "source": [
    "df['Salary']=pd.to_numeric(df['Salary'])\n",
    "team_position_salary=df.groupby(['Team','Position'])['Salary'].sum().reset_index()\n",
    "max_salary_index=team_position_salary['Salary'].idxmax()\n",
    "hightest_spending_team=team_position_salary.loc[max_salary_index,'Team']\n",
    "hightest_spending_position=team_position_salary.loc[max_salary_index,'Position']\n",
    "print(\"Team with highest spending :\",hightest_spending_team)\n",
    "print(\"Postion with highest spending :\",hightest_spending_position)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "9f0c29d4",
   "metadata": {},
   "source": [
    "##### 5.Find if there is any correlation between age and salary , represent it visually."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "6a0a211d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "df.plot.scatter(x='Age',y='Salary')\n",
    "plt.xlabel('Age')\n",
    "plt.ylabel('Salary')\n",
    "plt.title('Correlation between Age and Salary')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "d8fc3274",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.3"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
